# WordPress Development Guide

## Overview
WordPress is a widely used CMS among Generosity X clients. While it offers flexibility, modifying theme files directly in production can lead to serious issues, including PHP errors that may disable both the site and the WordPress backend.

### Important Notes on Editing WordPress Files:
- **Avoid editing theme files directly in production.** A single PHP syntax error can break the site and prevent access to the WordPress admin panel.
- **FTP/SSH access is often unavailable.** Since many client environments do not provide direct access to files, developers must find alternative solutions.
- **Use a PHP validator before saving code changes.** This helps catch syntax errors before applying them. [PHP Syntax Validator](https://phpcodechecker.com/)
- **Avoid modifying the `functions.php` file.** A mistake in this file can make the admin panel inaccessible, requiring intervention from hosting support.
- **Utilize WordPress-approved methods for customization**, such as page builders or custom plugins when necessary.

## Page Builders
Many Generosity X client websites rely on **Beaver Builder** and **Elementor** for page design and content structuring. These tools provide a safer and more efficient alternative to modifying template files directly.

### Beaver Builder
- **Drag-and-drop interface** allows easy content updates without coding.
- **Reusable modules and templates** speed up development.
- **Custom HTML and CSS sections** can be used for advanced customizations.
- **Theme compatibility** ensures that changes are not lost during updates.

### Elementor
- **Widget-based structure** makes it highly customizable.
- **Global styles and templates** allow consistency across the site.
- **Pro version supports dynamic content** for advanced use cases.
- **Custom code sections** should be validated before applying.

## Advanced Custom Fields (ACF)
Many client projects use **Advanced Custom Fields (ACF)** for managing structured data. This allows developers to create custom fields without modifying theme files.

### Best Practices for ACF:
- **Use ACF field groups** to organize custom fields logically.
- **Avoid direct file modifications**; instead, use ACF’s built-in options.
- **Ensure compatibility with page builders** by testing field output.
- **Use the ACF JSON feature** to sync field settings across environments.

## Additional Recommendations
- **Test all changes in a staging environment before deploying to production.**
- **Use a child theme instead of modifying the parent theme.**
- **Leverage custom plugins for site-specific PHP changes.**
- **Always validate custom PHP and JavaScript before applying changes.**

Following these best practices will help maintain site stability and avoid unnecessary downtime. If in doubt, consult with the project lead before making significant modifications.
