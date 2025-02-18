# Introduction to VWO

VWO (Visual Website Optimizer) is a powerful A/B testing and conversion optimization tool used to modify and test variations of web pages. Unlike a CMS, **VWO is merely an overlay and does not provide an easy way to add new content**. Instead, it allows you to modify existing elements on a page using a limited HTML editor. This can make complex changes challenging, especially when working with dynamic content or needing to add entirely new sections.

### **Key Limitations to Keep in Mind:**
- **No built-in CMS functionality:** You can only edit existing content; adding entirely new sections is difficult.
- **Limited HTML editor:** Changes must be made using a basic text editor within the platform.
- **Images must be pre-hosted:** You cannot upload images directly in VWO; instead, they must already be hosted on their WordPress site.

## Creating Variations in VWO

### **Step 1: Setting Up a Test**
1. Log in to your **VWO Dashboard**.
2. Navigate to **Testing > A/B Testing** and click on **Create**.
3. Enter the **URL** of the page you want to modify.
4. Choose whether to edit the page using **Visual Editor** or **Code Editor**.

### **Step 2: Editing the Page**
- **Using the Visual Editor:** Click on any element (text, button, image) to modify it.
- **Using the Code Editor:** Make direct changes to the HTML, CSS, or JavaScript for more advanced modifications.
- **Replacing Images:** Since images must be hosted externally, insert the image using an `<img>` tag and a direct URL.

### **Step 3: Setting Goals and Targeting**
1. Define a **goal** (e.g., form submission, button clicks, conversions).
2. Set the **target audience** (e.g., all visitors, mobile users, specific referral traffic).
3. Configure traffic allocation between your original and variant versions.

### **Step 4: Running and Analyzing the Test**
1. Launch the test and monitor performance in **VWO Reports**.
2. Look for statistical significance before implementing changes permanently.
3. Once satisfied with the results, apply the winning variation or start a new iteration.

## Hacking VWO to Add New Content
While VWO does not allow you to create entirely new sections easily, you can "hack" the system by hijacking existing sections. Since VWO functions similarly to React, where you can only modify a single element at a time, you can work around this by wrapping an existing section in a `<div>` and inserting additional elements above or below it.

### **How to Hijack a Section:**
1. Identify a section that allows HTML edits.
2. Wrap the existing content inside a `<div>`.
3. Use JavaScript or inline HTML to insert new content before or after it.

**Example:**
```html
<div>
    <div id="existing-content">
        Original Section Content
    </div>
    <div id="new-content">
        New Injected Content
    </div>
</div>
```
