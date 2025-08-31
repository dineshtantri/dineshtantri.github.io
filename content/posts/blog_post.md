+++
date = '2025-08-27T22:17:58+05:30'
draft = false
title = 'Redis Versus OpenSearch'
tags = ['search', 'performance']
+++

## Redis vs OpenSearch: A Real-World Performance Benchmark

In the world of search engines, choosing the right technology can make or break your application's performance. Today, we're diving deep into a comprehensive benchmark comparing two powerhouse search solutions: Redis 8.2 (with RediSearch and RedisJSON) against OpenSearch 2.11.

## The Challenge: Real-World Geographic Search

Instead of synthetic data, this benchmark uses the GeoNames cities15000 dataset - 32,325+ real city records from around the world. Each record contains 19 fields including geographic coordinates, population data, administrative codes, and demographic information. This represents the kind of complex, multi-dimensional data that real applications actually search through.

## Architecture Overview

### Redis Setup: The Speed Demon
- **Engine**: Redis Stack with RediSearch + RedisJSON modules
- **Storage**: Memory-based with JSON document structure
- **Schema**: Optimized TEXT, NUMERIC, and TAG fields
- **Key Structure**: `city:{geonameid}` prefix pattern

### OpenSearch Setup: The Full-Text Powerhouse  
- **Engine**: OpenSearch 2.11.1 with Lucene backend
- **Storage**: Disk-based with custom analyzers
- **Schema**: Geo-point mappings with asciifolding
- **Features**: Completion suggesters and advanced text analysis

In our case, we will run these off Docker.

## The Data Pipeline

Both engines process identical city records but optimize storage differently:

**Redis Approach**: Creates a search index (`cities_index`) with document keys like `city:2643743` for London, storing the full JSON document alongside searchable field indexes.

**OpenSearch Approach**: Uses a `cities` index with specialized geo_point fields for coordinates and custom analyzers for handling international city names with accent-folding.

## Query Patterns: Apples to Apples Comparison

The benchmark tests 10 representative query patterns:

1. **Text Search**: Finding cities by name with fuzzy matching
2. **Country Filters**: `@country_code:US` vs country-specific queries
3. **Population Ranges**: `@population:[500000 +inf]` for large cities
4. **Geographic Bounding Boxes**: Latitude/longitude range queries
5. **Complex Combinations**: Multi-field filters with text search

Both engines support equivalent functionality, but with different syntaxes—Redis uses FT.SEARCH commands while OpenSearch uses Elasticsearch DSL.

## Performance Results: The Numbers Don't Lie

### Single Query Performance
- **Redis**: Sub-millisecond latencies (0.3-0.7ms average)
- **OpenSearch**: 45-60ms latencies

### Concurrent Load Testing
- **Redis**: 2,000-10,000 requests per second
- **OpenSearch**: 200-300 requests per second

### Statistical Deep Dive
The benchmark framework measures mean, median, P95, and P99 latencies using ThreadPoolExecutor-based load generation, providing comprehensive statistical analysis beyond simple averages.

## When to Choose Which?

### Choose Redis When:
- **Ultra-low latency** is critical (real-time applications)
- You need **exact match performance** 
- **Simple deployment** is preferred
- Memory usage is acceptable for your dataset size

### Choose OpenSearch When:
- **Complex text analysis** is required
- You need **advanced search features** (suggesters, highlighting)
- **Large datasets** that don't fit in memory
- **Analytics and aggregations** are important

## The Technical Implementation

The project provides a complete benchmarking framework with:

```bash
# Quick start
docker-compose up -d
pip install -r requirements.txt

# Load data into both engines
python load_cities_data.py
python load_opensearch_data.py

# Run the benchmark
python benchmark_comparison.py --iterations 50 --concurrent-users 20
```

Interactive demos let you test queries manually:
```bash
python search_demo.py --interactive
python opensearch_demo.py --interactive
```

## Key Takeaways

1. **Performance Gap**: Redis delivers 100x faster query response times
2. **Throughput Difference**: Redis handles 10-30x more concurrent requests
3. **Use Case Alignment**: Both excel in their intended scenarios
4. **Real-World Testing**: Using actual geographic data provides meaningful insights

## Beyond the Benchmark

Redis shines for real-time applications where every millisecond counts, while OpenSearch excels at complex search scenarios with rich text analysis and large-scale data processing.

Here is the link to the repo: https://github.com/dineshtantri/redis-opensearch 