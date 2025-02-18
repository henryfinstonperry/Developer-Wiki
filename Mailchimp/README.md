# Mailchimp Guide

## Best Practices
- **Always verify the business account** before making edits to templates or campaigns.
- **Duplicate or create new templates/emails for testing.** Avoid modifying existing ones to prevent unintended changes to live campaigns.
- **Be extra cautious with sending test emails.** Never send test emails to an actual mailing list. Always double-check recipients before sending proof/test emails.

## Creating Table-Based Email Templates
Table-based layouts are the most reliable way to design emails, ensuring proper rendering across various email clients. Since many email clients (such as Outlook) do not fully support modern CSS, using tables for structure is essential.

### Steps to Create a Table-Based Email Template:
1. **Use the Mailchimp Template Builder**
   - Navigate to **Campaigns > Email Templates** in Mailchimp.
   - Choose **Create Template** and select the **Code Your Own** option if you prefer custom HTML.

2. **Manually Code an HTML Table-Based Layout**
   - Use `<table>` elements to structure your content.
   - Use `width="100%"` on parent tables to ensure full responsiveness.
   - Apply inline styles for better compatibility:
   ```html
   <table width="100%" cellpadding="0" cellspacing="0" border="0">
       <tr>
           <td align="center">
               <table width="600" cellpadding="10" cellspacing="0" border="0">
                   <tr>
                       <td style="font-family: Arial, sans-serif; font-size: 16px; color: #333;">
                           Welcome to our email newsletter!
                       </td>
                   </tr>
               </table>
           </td>
       </tr>
   </table>
   ```

3. **Optimize for Mobile Devices**
   - Use **media queries** for responsive design.
   - Ensure tables are fluid and adjust properly in smaller screens.
   - Example:
   ```css
   @media screen and (max-width: 600px) {
       table[class="responsive-table"] {
           width: 100% !important;
       }
   }
   ```


## Mailchimp Merge Fields & Editable Divs

### **Mailchimp Merge Fields**
Mailchimp allows the use of **merge tags** to personalize emails with subscriber data. These are placeholders that dynamically pull information from the audience list.

#### **Common Merge Tags**
- `*|FNAME|*` – First name of the recipient
- `*|LNAME|*` – Last name of the recipient
- `*|EMAIL|*` – Email address
- `*|DATE|*` – The current date
- `*|LIST:NAME|*` – The name of the email list
- `*|MC_PREVIEW_TEXT|*` – Adds preview text for email clients

**Example Usage:**
```html
<p>Hello *|FNAME|*,</p>
<p>Thank you for subscribing to our newsletter!</p>
```

#### **Custom Merge Fields**
To create custom fields:
1. Go to **Audience > Settings > Audience fields and merge tags**.
2. Add a new field (e.g., `Birthday`).
3. Assign a merge tag like `*|BIRTHDAY|*` and use it in your email template.

### **Creating Editable Divs in Mailchimp**
If you're designing custom templates and want content to be **editable in Mailchimp's campaign builder**, you can use Mailchimp’s editable regions.

#### **Using the `mc:edit` Attribute**
You can specify sections of an email template as editable by using the `mc:edit` attribute:
```html
<div mc:edit="header">
    <h1>Welcome to Our Newsletter</h1>
</div>
```
- In the Mailchimp editor, users can modify this section without affecting the template structure.
- Each `mc:edit` block should have a **unique name**.

#### **Editable Image Example**
```html
<img mc:edit="hero_image" src="default-image.jpg" width="600" alt="Hero Image">
```
Users can replace the image in the Mailchimp editor without modifying the HTML.

#### **Additional Customization**
- `mc:repeatable` – Allows a section to be duplicated or removed in the editor.
- `mc:hideable` – Lets users toggle the visibility of a section.
- `mc:label` – Adds a descriptive name to editable regions.

**Example with Multiple Editable Sections:**
```html
<table width="100%">
    <tr>
        <td mc:edit="title">
            <h2>Special Offer Just for You!</h2>
        </td>
    </tr>
    <tr mc:repeatable="feature_block">
        <td mc:edit="feature_text">
            <p>Exclusive discount available for a limited time.</p>
        </td>
    </tr>
</table>
```

## Helpful Resources
- [Mailchimp's Guide to Custom HTML Templates](https://mailchimp.com/help/create-custom-html-template/)
- [Email Development Best Practices](https://www.campaignmonitor.com/resources/guides/how-to-code-html-emails/)
- [Litmus – Email Testing Tool](https://www.litmus.com/)
- [Can I Email – Email Client Support Checker](https://www.caniemail.com/)
- [Mailchimp Merge Tags Guide](https://mailchimp.com/help/getting-started-with-merge-tags/)
- [Editable Content in Mailchimp](https://mailchimp.com/help/editable-content-areas/)
- [Mailchimp Custom Templates](https://mailchimp.com/help/create-custom-html-template/)
