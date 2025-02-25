# WordPress Development Guide

## Overview
WordPress is a widely used CMS among Generosity X clients. Be cautious; modifying theme files directly in production can lead to serious issues, including PHP errors that may disable both the site and the WordPress backend.

### Important Notes on Editing WordPress Theme Files:
- **Avoid editing theme files directly in production.** A single PHP syntax error can break the site and prevent access to the WordPress admin panel.
- **FTP/SSH access is often unavailable.** Since many client environments do not provide direct access to files, developers must find alternative solutions.
- **Use a PHP validator before saving code changes.** This helps catch syntax errors before applying them. [PHP Syntax Validator](https://phpcodechecker.com/).
- **Avoid modifying the `functions.php` file.** A mistake in this file can make the admin panel inaccessible, requiring intervention from hosting support.

## Page Builders
Many Generosity X client websites rely on **Beaver Builder** and **Elementor** for page design and content structuring. These tools provide a safer and more efficient alternative to modifying template files directly.

### Hacking Page Builders
There are cases where their default functionality is limiting. In such situations, you can employ a few tricks to work around these limitations:

#### Inserting Extra HTML and CSS
- Many page builders allow for **custom HTML blocks** where you can directly insert `<div>`, `<span>`, or other elements to achieve finer control over layout and styling.
- When using CSS, **add custom classes and IDs** in the page builder’s settings, then style them using the theme’s Additional CSS section or a child theme’s stylesheet.
- Some builders strip out certain tags (e.g., `<script>` or `<iframe>`), so you may need to test how they process raw code.

#### Executing JavaScript or PHP via Shortcodes
- If direct JavaScript or PHP is filtered out (especially in environments with security plugins), consider using a plugin that allows you to execute **custom scripts via shortcodes**.
- Plugins like **WPCode (formerly Code Snippets)** or **Insert PHP Code Snippet** let you define reusable functions and call them via shortcodes within the builder.
For JavaScript-heavy modifications, you may need to use a **custom JavaScript injector** plugin or enqueue scripts via functions.php (if permitted).

## Advanced Custom Fields (ACF)
Many client projects use **Advanced Custom Fields (ACF)** for managing structured data. This allows you to create custom fields without modifying theme files.

### Best Practices for ACF:
- **Use ACF field groups** to organize custom fields logically.
- **Avoid direct file modifications**; instead, use ACF’s built-in options.
- **Ensure compatibility with page builders** by testing field output.
- **Use the ACF JSON import/output feature** to sync field settings across environments.

## Additional Recommendations
- **Test all changes in a staging environment before deploying to production.**
- **Use a child theme instead of modifying the parent theme.**
- **Leverage custom plugins for site-specific PHP changes.**
- **Always validate custom PHP and JavaScript before applying changes.**

If in doubt, consult with GX before making significant modifications.

## Welcome Hall Mission Campaigns
Welcome Hall Mission uses a unique configuration of ACF to handle their rotating giving campaigns. You can safely create and preview campaigns on their live site without the need for a staging environment.

### Building a Campaign
- Navigate to [Campaigns > Set Campaign](https://welcomehallmission.com/wp-admin/edit.php?post_type=campaigns&page=set-campaign) to set the live campaign. The dropdown list is populated by published Campaign posts. **Caution:** The Update button on this page has an immediate affect on the live site. Preview and test adequately before confirming.
- Navigate to [Campaigns > Campaigns](https://welcomehallmission.com/wp-admin/edit.php?post_type=campaigns) to view all Campaign posts. Use recent ones for reference as some fields have become unnecessary when the Campaign pages are rendered.
- Here are the fields you need to set for the Campaign:
  - **Home Background Image** (required)
  - **Home Headline (English)** (required)
  - **Home Subheadline (English)**
  - **Home Button URL (English)** (required)
  - **Home Button Text (English)** (required)
  - **Home Headline (Français)** (required)
  - **Home Subheadline (Français)**
  - **Home Button URL (Français)** (required)
  - **Home Button Text (Français)** (required)
- And here are the outdated fields that you *still need to set* for the Campaign to work:
  - The following can be populated with any image: *Donate Background Image*, *Donate Background Image - French*, *Thank You Background Image - English*, *Thank You Background Image - French*
  - The following can be populated with a space or "N/A": *Donate Headline (English)*, *Thank You Headline (English)*, *Donate Headline (Français)*, *Thank You Headline (Français)*

### Testing a Campaign
- You should only need to preview the Home pages in English and French; the other pages are no longer in use since they switched to a new popup donation form.
- When you click on "Preview Accueil" (French Home Page), it will show in English. This is a bug in their multi-lingual domain service. All you need to do is change "welcomehallmission.com" in the URL to "missionbonaccueil.com", keeping the URL parameters. In the end your French preview URL will be "https://missionbonaccueil.com/?preview_campaign={{campaign_id}}"
