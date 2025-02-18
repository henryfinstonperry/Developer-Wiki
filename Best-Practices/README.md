# Best Practices

## Handling Social Media In-App Browsers
GX runs many paid campaigns on social media platforms, leading to high click-through rates from in-app browsers. Unfortunately, these browsers have several limitations:

### **Common Issues:**
- In-app browsers (Facebook, Instagram, X) tend to suppress or ignore JavaScript.
- Embedded iframes or script tags (e.g., for donation platforms) may not load correctly.
- Tracking scripts and certain third-party integrations may fail to execute.

### **Workarounds:**
- **Swap embedded forms for buttons with external links.** Instead of embedding donation forms, provide a clear CTA button that opens the form in the user's default browser.
- **Use PHP instead of JavaScript where possible.** If your form requires JavaScript, consider shifting logic to the backend to avoid client-side suppression.
- **Communicate these limitations to clients.** In some cases, no workaround exists due to Meta’s restrictive in-app browser policies. Let clients know what’s possible and what isn’t.

## Troubleshooting WordPress Builders
Page builders like Elementor and Beaver Builder can sometimes fail to save or load correctly. This can be due to browser-specific issues, cache problems, or conflicts with other plugins.

### **Solutions:**
- **Switch browsers.** If the builder isn’t working in Chrome, try Firefox (or vice versa). Some plugins work better in certain browsers.
- **Clear cache and refresh.** Browser and plugin caches can sometimes cause issues with saving changes.
- **Disable conflicting plugins.** If switching browsers doesn’t work, try temporarily disabling other plugins to identify conflicts.

## Installing Additional Plugins When Necessary
When direct access to theme templates is unavailable, plugins can often provide necessary functionality. For example, GX often requires notification bars (commonly referred to as emergency bars). Look for lightweight and easily customizable options.

### **Guidelines for Using Plugins:**
- **Use reputable plugins.** Check ratings, reviews, and update frequency before installing.
- **Consider performance impact.** Some plugins can slow down the site; test before deploying.
- **Clear any installation with GX first.** Let them know what you are installing and why. 
