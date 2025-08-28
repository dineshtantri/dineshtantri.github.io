# Digithos Blog

A personal blog built with Hugo and customized with the Archie theme, featuring a clean, monthly-organized post layout.

## 🏗️ Project Structure

```
my-hugo-site/
├── content/
│   ├── about.md              # About page with profile
│   └── posts/               # Blog posts directory
│       ├── my-first-post.md
│       └── blog_post.md
├── layouts/
│   ├── index.html           # Custom home page template (overrides theme)
│   └── partials/
│       └── footer.html      # Custom footer with RSS feed integration
├── static/
│   ├── css/
│   │   └── custom.css       # Custom CSS overrides
│   └── images/              # Site images including profile photo
├── themes/
│   └── archie/              # Archie theme files
├── hugo.toml                # Hugo configuration
└── README.md                # This file
```

## 🎨 Design Features

### Custom Home Page Layout  
- **Monthly Organization**: Posts are grouped by month (e.g., "2025 August")
- **Clean Typography**: Minimal design inspired by modern blog layouts
- **Title-Only Display**: Shows only post titles and dates (no content summaries)
- **Chronological Grouping**: Automatically organized by publication month

### Theme Customizations
- **Removed Heading Prefixes**: Fixed the Archie theme's CSS that added `##` symbols before headings
- **Responsive Design**: Adapts to both desktop and mobile screens
- **Dark Mode Support**: Automatically follows system preferences
- **RSS Feed Integration**: Orange RSS button in footer linking to blog post feed

## 🚀 Getting Started

### Prerequisites
- Hugo (Static Site Generator)
- Git (for version control)

### Installation & Setup

1. **Install Hugo** (if not already installed):
   ```bash
   # Windows (using Chocolatey)
   choco install hugo-extended
   
   # macOS (using Homebrew)
   brew install hugo
   
   # Or download from: https://github.com/gohugoio/hugo/releases
   ```

2. **Clone and Run**:
   ```bash
   cd my-hugo-site
   hugo server
   ```

3. **Access Your Site**:
   Open your browser to `http://localhost:1313`

### Creating New Posts

1. Create a new Markdown file in `content/posts/`:
   ```bash
   hugo new posts/my-new-post.md
   ```

2. Edit the frontmatter and content:
   ```markdown
   +++
   date = '2025-08-28T10:00:00+05:30'
   draft = false
   title = 'My New Post Title'
   tags = ['tag1', 'tag2']
   +++
   
   ## Your Content Here
   
   Write your blog post content using Markdown syntax.
   ```

3. The post will automatically appear on the home page, grouped by month.

## 🔧 Configuration Details

### Hugo Configuration (`hugo.toml`)
- **Theme**: Archie - minimal and clean design
- **Markdown Processing**: Goldmark with GitHub-style heading IDs
- **Syntax Highlighting**: Monokai color scheme
- **Custom CSS**: Loads `css/custom.css` for theme overrides

### Custom Features Implemented

#### 1. Monthly Post Grouping
**File**: `layouts/index.html`
- Uses Hugo's `GroupByDate` function to organize posts by month
- Format: "2006 January" produces "2025 August" style headers
- Automatically sorts posts chronologically

#### 2. Template Fingerprinting Error Fix
**Problem Solved**: Hugo template errors preventing site rendering
**Root Cause**: Theme tried to fingerprint external CSS files but failed with `<nil> can not be transformed`
**Solution**: Embedded critical CSS directly in templates to bypass fingerprinting

#### 3. Critical Fix: Markdown Heading Rendering
**Problem Solved**: Archie theme was displaying raw `##` symbols instead of formatted headings
**Scope**: Affected all pages - home page, individual blog posts, about page
**Root Cause**: Theme CSS intentionally added decorative Markdown prefixes via `::before` pseudo-elements:
```css
h1::before { content: '# '; }
h2::before { content: '## '; }
```

**Final Solution**: Added comprehensive CSS overrides to `layouts/partials/head.html` (site-wide):
```css
/* Global fix: Remove ## symbols from ALL headings on ALL pages */
h1::before, h2::before, h3::before, h4::before, h5::before, h6::before { 
    content: '' !important; 
}
/* Additional targeting for comprehensive coverage */
article h1::before, article h2::before, /* ... more selectors ... */
main h1::before, main h2::before { content: '' !important; }
```
**Result**: Clean heading display across entire site with proper HTML formatting

#### 4. About Page with Profile
- Circular profile image with responsive sizing
- Professional bio highlighting work experience
- Clean side-by-side layout on desktop

#### 5. RSS Feed Integration
**Problem Solved**: Provide easy subscription method for blog readers  
**Implementation**: Custom footer partial with RSS feed button  
**Location**: Orange RSS icon in footer next to social media icons  
**Feed URL**: `/posts/index.xml` (contains all blog posts)  

**Features**:
- Standard RSS orange button (#ff6600 color)
- Hover effect with darker orange (#ff4500)
- Links to blog posts feed (not site-wide feed)
- Proper RSS metadata and attributes
- Responsive design matching site theme

**RSS Feeds Available**:
- **Main Blog Posts**: https://dineshtantri.github.io/posts/index.xml
- **Site-wide Feed**: https://dineshtantri.github.io/index.xml (includes all content)
- **Tag-specific Feeds**: Available for each tag (e.g., `/tags/hugo/index.xml`)

**Implementation Files**:
- `layouts/partials/footer.html` - Custom footer with RSS integration
- RSS feeds auto-generated by Hugo in `/public/*.xml` files

## 📝 Content Guidelines

### Writing Blog Posts
1. **Use Markdown**: All standard Markdown syntax is supported
2. **Add Tags**: Include relevant tags in the frontmatter for better organization
3. **Set Dates**: Proper date formatting ensures correct monthly grouping
4. **Draft Mode**: Set `draft = true` to hide posts while writing

### Markdown Examples
```markdown
## Headings
Use ## for main sections, ### for subsections

**Bold text** and *italic text*

- Bullet points
- Are supported

```code blocks```
Are highlighted automatically
```

## 🎯 Customization Options

### Changing Colors or Styles
1. Edit `static/css/custom.css` to override theme styles
2. The CSS includes detailed comments explaining each override
3. Test changes with `hugo server` for live reload

### Adding New Sections
1. Create new directories in `content/` 
2. Update `hugo.toml` navigation menu if needed
3. Create custom layouts in `layouts/` if required

### Modifying the Home Page
1. Edit `layouts/index.html` for layout changes
2. The template includes detailed Hugo comments
3. Uses Hugo template functions like `range`, `where`, and `GroupByDate`

## 🛠️ Troubleshooting

### Common Issues

1. **Hugo Command Not Found**
   - Ensure Hugo is installed and in your PATH
   - Restart your terminal after installation

2. **Changes Not Showing**
   - Hard refresh your browser (Ctrl+F5 or Cmd+Shift+R)
   - Check that `hugo server` is running without errors

3. **Markdown Not Rendering**
   - Verify frontmatter is properly formatted with `+++`
   - Check that `unsafe = true` is set in `hugo.toml`

4. **Template Fingerprinting Errors**
   - **Error**: `error calling fingerprint: <nil> can not be transformed`
   - **Cause**: Hugo can't process external CSS files for fingerprinting
   - **Solution**: We use embedded CSS in templates instead of external files
   - **Prevention**: Avoid using `customcss` parameter with complex external CSS

5. **## Symbols Appearing in Headings** ⚠️ **CRITICAL ISSUE - RESOLVED**
   - **Error**: Raw `##` Markdown symbols showing instead of properly formatted headings
   - **Cause**: Archie theme intentionally adds Markdown prefixes via `::before` CSS pseudo-elements
   - **Impact**: Affected ALL pages - home page titles, individual blog post headings, about page
   - **Solution**: Comprehensive CSS overrides in `layouts/partials/head.html` (site-wide)
   - **Verification**: Check that headings like "My First Post", "Welcome to My Blog!" display cleanly
   - **Files Modified**: `layouts/partials/head.html` with detailed CSS comments explaining the fix

## 📚 Learning Resources

### Hugo Documentation
- [Hugo Docs](https://gohugo.io/documentation/)
- [Hugo Template Functions](https://gohugo.io/functions/)
- [Markdown Guide](https://www.markdownguide.org/)

### Theme Information
- [Archie Theme](https://github.com/athul/archie)
- [Hugo Themes Gallery](https://themes.gohugo.io/)

## 🚢 Deployment

To deploy your site to production:

1. **Update Configuration**:
   ```toml
   baseURL = "https://your-domain.com"
   ```

2. **Build Static Files**:
   ```bash
   hugo
   ```

3. **Deploy the `public/` folder** to your hosting provider

## 📄 License

This project is open source. The Archie theme is licensed under MIT.

## 🤝 Contributing

Feel free to fork this repository and customize it for your own blog. The code includes detailed comments to help you understand how everything works.

---

Built with ❤️ using Hugo and the Archie theme. Customized for the Digithos blog.