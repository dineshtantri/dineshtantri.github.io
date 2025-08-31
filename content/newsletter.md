+++
date = '2025-08-29T17:00:00+05:30'
draft = false
title = ''
hidedate = true  # Hide date display on this page
+++



<div style="max-width: 400px; margin: 2rem 0;">
    <div id="mlb2-30249695" class="ml-form-embedContainer ml-subscribe-form ml-subscribe-form-30249695">
      <div class="ml-form-align-center">
        <div class="ml-form-embedWrapper embedForm">
          <div class="ml-form-embedBody ml-form-embedBodyDefault row-form">
            <div class="ml-form-embedContent">
              <h4>Subscribe to Newsletter</h4>
              <p>Get notified about new posts and updates</p>
            </div>
            <form class="ml-block-form" action="https://assets.mailerlite.com/jsonp/1766565/forms/164078619046446571/subscribe" data-code="" method="post">
              <div class="ml-form-formContent">
                <div class="ml-form-fieldRow ml-last-item">
                  <div class="ml-field-group ml-field-email ml-validate-email ml-validate-required">
                    <input aria-label="email" aria-required="true" type="email" class="form-control" name="fields[email]" placeholder="your@email.com" autocomplete="email" required>
                  </div>
                </div>
              </div>
              <input type="hidden" name="ml-submit" value="1">
              <input type="hidden" name="anticsrf" value="true">
              <div class="ml-form-embedSubmit">
                <button type="submit" class="primary">Subscribe</button>
                <button disabled="disabled" style="display: none;" type="button" class="loading">
                  <div class="ml-form-embedSubmitLoad"></div>
                  <span class="sr-only">Loading...</span>
                </button>
              </div>
            </form>
          </div>
          <div class="ml-form-successBody row-success" style="display: none">
            <div class="ml-form-successContent">
              <h4>Thank you!</h4>
              <p>You have successfully joined the subscriber list.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
</div>



<style>
/* 
 * NEWSLETTER PAGE STYLING - DINESHTANTRI BLOG
 * 
 * This page provides a clean, dedicated newsletter signup experience
 * integrated with MailerLite for email marketing automation.
 * 
 * Key Features:
 * - MailerLite form integration with custom styling
 * - Theme-aware design (light/dark mode support)
 * - Date hiding for clean, timeless page appearance
 * - Responsive design matching site aesthetic
 * - Success/error handling for form submissions
 */

/* Hide date elements on newsletter page for clean, timeless appearance */
.post-date,
.meta,
.post-meta,
time,
.date {
    display: none !important;
}

/* 
 * MAILERLITE FORM CONTAINER STYLING
 * 
 * Override MailerLite's default styling to match the site's minimal aesthetic.
 * Focus on transparency, clean borders, and consistent spacing.
 */
.ml-form-embedContainer {
    max-width: 100% !important;  /* Full width container */
    width: 100% !important;      /* Responsive width */
}

.ml-form-embedWrapper {
    background-color: transparent !important;  /* No background, keeps page clean */
    border: 1px solid #ddd !important;        /* Subtle border for definition */
    border-radius: 8px !important;            /* Rounded corners for modern look */
    padding: 2rem !important;                 /* Generous padding for breathing room */
}

.ml-form-embedBody .ml-form-embedContent h4 {
    color: #333 !important;
    font-family: inherit !important;
    font-size: 1.3rem !important;
    font-weight: 500 !important;
    margin-bottom: 0.5rem !important;
}

.ml-form-embedBody .ml-form-embedContent p {
    color: #666 !important;
    font-family: inherit !important;
    font-size: 0.95rem !important;
    margin-bottom: 1.5rem !important;
}

.ml-form-fieldRow input {
    background-color: #fff !important;
    color: #333 !important;
    border: 1px solid #ddd !important;
    border-radius: 4px !important;
    font-family: inherit !important;
    font-size: 0.95rem !important;
    padding: 0.8rem 1rem !important;
    width: 100% !important;
    box-sizing: border-box !important;
}

.ml-form-fieldRow input:focus {
    border-color: #333 !important;
    outline: none !important;
}

.ml-form-fieldRow input::placeholder {
    color: #999 !important;
}

.ml-form-embedSubmit {
    margin-top: 1rem !important;
}

.ml-form-embedSubmit button {
    background-color: #333 !important;
    color: #fff !important;
    border: none !important;
    border-radius: 4px !important;
    font-family: inherit !important;
    font-size: 0.95rem !important;
    font-weight: 500 !important;
    padding: 0.8rem 2rem !important;
    cursor: pointer !important;
    transition: background-color 0.2s ease !important;
}

.ml-form-embedSubmit button:hover {
    background-color: #000 !important;
}

.ml-form-successContent h4 {
    color: #333 !important;
    font-family: inherit !important;
    font-size: 1.2rem !important;
    margin-bottom: 0.5rem !important;
}

.ml-form-successContent p {
    color: #666 !important;
    font-family: inherit !important;
    font-size: 0.95rem !important;
}

/* Dark mode support */
@media (prefers-color-scheme: dark) {
    .ml-form-embedWrapper {
        background-color: transparent !important;
        border-color: #333 !important;
    }
    
    .ml-form-embedBody .ml-form-embedContent h4,
    .ml-form-successContent h4 {
        color: #fff !important;
    }
    
    .ml-form-embedBody .ml-form-embedContent p,
    .ml-form-successContent p {
        color: #aaa !important;
    }
    
    .ml-form-fieldRow input {
        background-color: #2a2a2a !important;
        color: #fff !important;
        border-color: #555 !important;
    }
    
    .ml-form-fieldRow input:focus {
        border-color: #aaa !important;
    }
    
    .ml-form-fieldRow input::placeholder {
        color: #666 !important;
    }
    
    .ml-form-embedSubmit button {
        background-color: #555 !important;
    }
    
    .ml-form-embedSubmit button:hover {
        background-color: #777 !important;
    }
}

/* Manual theme overrides */
[data-theme="light"] .ml-form-embedWrapper {
    background-color: transparent !important;
    border-color: #ddd !important;
}

[data-theme="light"] .ml-form-embedBody .ml-form-embedContent h4,
[data-theme="light"] .ml-form-successContent h4 {
    color: #333 !important;
}

[data-theme="light"] .ml-form-embedBody .ml-form-embedContent p,
[data-theme="light"] .ml-form-successContent p {
    color: #666 !important;
}

[data-theme="dark"] .ml-form-embedWrapper {
    background-color: transparent !important;
    border-color: #333 !important;
}

[data-theme="dark"] .ml-form-embedBody .ml-form-embedContent h4,
[data-theme="dark"] .ml-form-successContent h4 {
    color: #fff !important;
}

[data-theme="dark"] .ml-form-embedBody .ml-form-embedContent p,
[data-theme="dark"] .ml-form-successContent p {
    color: #aaa !important;
}
</style>

<script>
/*
 * IMPORTANT: Form ID Mismatch Issue (Documented for debugging)
 * - Form submits to: 164078619046446571 (from action URL)
 * - Form wrapper uses: 30249695 (line 11)
 * - Success callback uses: 30249695 (this function)
 * This mismatch may prevent proper success handling.
 */
function ml_webform_success_30249695() {
    var $ = ml_jQuery || jQuery;
    if (typeof $ !== 'undefined') {
        $('.ml-subscribe-form-30249695 .row-success').show();
        $('.ml-subscribe-form-30249695 .row-form').hide();
    } else {
        // Fallback without jQuery
        const successDiv = document.querySelector('.ml-subscribe-form-30249695 .row-success');
        const formDiv = document.querySelector('.ml-subscribe-form-30249695 .row-form');
        if (successDiv && formDiv) {
            successDiv.style.display = 'block';
            formDiv.style.display = 'none';
        }
    }
}
</script>
<script src="https://groot.mailerlite.com/js/w/webforms.min.js?v176e10baa5e7ed80d35ae235be3d5024" type="text/javascript"></script>