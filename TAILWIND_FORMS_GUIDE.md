# Tailwind CSS Form Styling Guide - Manual Utilities

This guide shows you how to style forms manually with Tailwind CSS utilities (no forms plugin needed).

## Table of Contents
1. [Text Inputs](#text-inputs)
2. [Labels](#labels)
3. [Buttons](#buttons)
4. [Checkboxes](#checkboxes)
5. [Radio Buttons](#radio-buttons)
6. [Select Dropdowns](#select-dropdowns)
7. [Textareas](#textareas)
8. [Form States](#form-states)
9. [Complete Examples](#complete-examples)

---

## Text Inputs

### Basic Text Input
```jsx
<input
  type="email"
  className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
  placeholder="you@example.com"
/>
```

**Classes Explained:**
- `block w-full` - Full width block element
- `rounded-md` - Medium rounded corners
- `border border-gray-300` - Gray border (1px)
- `px-3 py-2` - Padding: 12px horizontal, 8px vertical
- `text-gray-900` - Dark gray text color
- `placeholder-gray-400` - Light gray placeholder
- `focus:border-indigo-500` - Indigo border on focus
- `focus:outline-none` - Remove default browser outline
- `focus:ring-2 focus:ring-indigo-500` - 2px indigo focus ring
- `shadow-sm` - Small shadow for depth

### Password Input
```jsx
<input
  type="password"
  className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
  placeholder="••••••••"
/>
```

---

## Labels

### Standard Label
```jsx
<label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-1">
  Email address
</label>
```

**Classes Explained:**
- `block` - Block element (full width)
- `text-sm` - Small text size (14px)
- `font-medium` - Medium font weight (500)
- `text-gray-700` - Medium gray text
- `mb-1` - Margin bottom: 4px

### Required Label with Asterisk
```jsx
<label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-1">
  Email address <span className="text-red-500">*</span>
</label>
```

---

## Buttons

### Primary Button
```jsx
<button
  type="submit"
  className="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 transition-colors"
>
  Sign in
</button>
```

**Classes Explained:**
- `w-full` - Full width
- `flex justify-center` - Center content with flexbox
- `py-2 px-4` - Padding: 8px vertical, 16px horizontal
- `border border-transparent` - Transparent border (maintains size)
- `rounded-md` - Medium rounded corners
- `shadow-sm` - Small shadow
- `text-sm font-medium` - Small, medium-weight text
- `text-white bg-indigo-600` - White text on indigo background
- `hover:bg-indigo-700` - Darker on hover
- `focus:outline-none` - Remove default outline
- `focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500` - Focus ring with offset
- `transition-colors` - Smooth color transitions

### Secondary Button
```jsx
<button
  type="button"
  className="w-full flex justify-center py-2 px-4 border border-gray-300 rounded-md shadow-sm text-sm font-medium text-gray-700 bg-white hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 transition-colors"
>
  Cancel
</button>
```

### Icon Button
```jsx
<button
  type="button"
  className="inline-flex items-center px-3 py-2 border border-gray-300 shadow-sm text-sm font-medium rounded-md text-gray-700 bg-white hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
>
  <svg className="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    {/* icon path */}
  </svg>
  Button Text
</button>
```

---

## Checkboxes

### Standard Checkbox
```jsx
<input
  type="checkbox"
  id="remember-me"
  className="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500"
/>
<label htmlFor="remember-me" className="ml-2 block text-sm text-gray-900">
  Remember me
</label>
```

**Classes Explained:**
- `h-4 w-4` - 16px x 16px size
- `rounded` - Rounded corners
- `border-gray-300` - Gray border
- `text-indigo-600` - Checked state color
- `focus:ring-indigo-500` - Focus ring color

### Checkbox with Full-Width Wrapper
```jsx
<div className="flex items-start">
  <input
    id="terms"
    type="checkbox"
    className="h-4 w-4 mt-1 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500"
  />
  <label htmlFor="terms" className="ml-2 block text-sm text-gray-900">
    I agree to the Terms of Service
  </label>
</div>
```

---

## Radio Buttons

### Radio Button Group
```jsx
<fieldset>
  <legend className="block text-sm font-medium text-gray-700 mb-2">
    Email notifications
  </legend>
  <div className="space-y-2">
    <div className="flex items-center">
      <input
        id="notify-all"
        name="notifications"
        type="radio"
        value="all"
        defaultChecked
        className="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-500"
      />
      <label htmlFor="notify-all" className="ml-2 block text-sm text-gray-900">
        All updates
      </label>
    </div>
    <div className="flex items-center">
      <input
        id="notify-important"
        name="notifications"
        type="radio"
        value="important"
        className="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-500"
      />
      <label htmlFor="notify-important" className="ml-2 block text-sm text-gray-900">
        Important only
      </label>
    </div>
  </div>
</fieldset>
```

**Classes Explained:**
- `space-y-2` - Vertical spacing between items (8px)
- `flex items-center` - Align radio and label vertically centered

---

## Select Dropdowns

### Standard Select
```jsx
<select
  id="country"
  className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
>
  <option value="">Select a country</option>
  <option value="us">United States</option>
  <option value="ca">Canada</option>
  <option value="uk">United Kingdom</option>
</select>
```

**Note:** Select dropdowns use the same classes as text inputs.

---

## Textareas

### Standard Textarea
```jsx
<textarea
  id="bio"
  rows="4"
  className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
  placeholder="Tell us about yourself..."
></textarea>
```

### Textarea with Character Count
```jsx
<div>
  <textarea
    id="message"
    rows="4"
    maxLength="500"
    className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
  ></textarea>
  <p className="mt-1 text-xs text-gray-500 text-right">0 / 500 characters</p>
</div>
```

---

## Form States

### Error State
```jsx
<div>
  <label htmlFor="email" className="block text-sm font-medium text-red-700 mb-1">
    Email address
  </label>
  <input
    id="email"
    type="email"
    className="block w-full rounded-md border-2 border-red-300 px-3 py-2 text-red-900 placeholder-red-300 focus:border-red-500 focus:outline-none focus:ring-2 focus:ring-red-500 shadow-sm"
    placeholder="you@example.com"
  />
  <p className="mt-1 text-sm text-red-600">This email is already taken</p>
</div>
```

**Error Classes:**
- `border-red-300` - Red border
- `text-red-900` - Red text
- `placeholder-red-300` - Red placeholder
- `focus:border-red-500` - Darker red on focus
- `focus:ring-red-500` - Red focus ring

### Success State
```jsx
<div>
  <label htmlFor="email" className="block text-sm font-medium text-green-700 mb-1">
    Email address
  </label>
  <input
    id="email"
    type="email"
    className="block w-full rounded-md border-2 border-green-300 px-3 py-2 text-green-900 placeholder-green-300 focus:border-green-500 focus:outline-none focus:ring-2 focus:ring-green-500 shadow-sm"
    placeholder="you@example.com"
  />
  <p className="mt-1 text-sm text-green-600">✓ Email is available</p>
</div>
```

### Disabled State
```jsx
<input
  type="email"
  disabled
  className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 bg-gray-100 cursor-not-allowed opacity-50 shadow-sm"
  placeholder="you@example.com"
/>
```

**Disabled Classes:**
- `bg-gray-100` - Light gray background
- `cursor-not-allowed` - Show not-allowed cursor
- `opacity-50` - 50% opacity

### Loading State
```jsx
<button
  type="submit"
  disabled
  className="w-full flex justify-center items-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 opacity-50 cursor-not-allowed"
>
  <svg className="animate-spin h-5 w-5 mr-2" viewBox="0 0 24 24">
    {/* spinner icon */}
  </svg>
  Processing...
</button>
```

---

## Complete Examples

### Login Form
```jsx
export default function Login() {
  const handleSubmit = (e) => {
    e.preventDefault();
    console.log('Form submitted');
  };

  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-100">
      <div className="max-w-md w-full space-y-8 p-8 bg-white rounded-lg shadow-md">
        <div>
          <h2 className="text-center text-3xl font-extrabold text-gray-900">
            Sign in to your account
          </h2>
        </div>
        <form className="mt-8 space-y-6" onSubmit={handleSubmit}>
          <div className="rounded-md shadow-sm space-y-4">
            <div>
              <label htmlFor="email" className="block text-sm font-medium text-gray-700">
                Email address
              </label>
              <input
                id="email"
                name="email"
                type="email"
                required
                className="mt-1 block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
                placeholder="you@example.com"
              />
            </div>
            <div>
              <label htmlFor="password" className="block text-sm font-medium text-gray-700">
                Password
              </label>
              <input
                id="password"
                name="password"
                type="password"
                required
                className="mt-1 block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
                placeholder="••••••••"
              />
            </div>
          </div>

          <div className="flex items-center justify-between">
            <div className="flex items-center">
              <input
                id="remember-me"
                name="remember-me"
                type="checkbox"
                className="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded"
              />
              <label htmlFor="remember-me" className="ml-2 block text-sm text-gray-900">
                Remember me
              </label>
            </div>

            <div className="text-sm">
              <a href="#" className="font-medium text-indigo-600 hover:text-indigo-500">
                Forgot your password?
              </a>
            </div>
          </div>

          <div>
            <button
              type="submit"
              className="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
            >
              Sign in
            </button>
          </div>
        </form>
      </div>
    </div>
  );
}
```

### Contact Form
```jsx
export default function ContactForm() {
  return (
    <div className="max-w-2xl mx-auto p-6">
      <h2 className="text-2xl font-bold text-gray-900 mb-6">Contact Us</h2>
      <form className="space-y-6">
        {/* Name Row */}
        <div className="grid grid-cols-1 gap-6 sm:grid-cols-2">
          <div>
            <label htmlFor="first-name" className="block text-sm font-medium text-gray-700 mb-1">
              First name
            </label>
            <input
              type="text"
              id="first-name"
              className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
            />
          </div>
          <div>
            <label htmlFor="last-name" className="block text-sm font-medium text-gray-700 mb-1">
              Last name
            </label>
            <input
              type="text"
              id="last-name"
              className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
            />
          </div>
        </div>

        {/* Email */}
        <div>
          <label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-1">
            Email
          </label>
          <input
            type="email"
            id="email"
            className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
          />
        </div>

        {/* Subject */}
        <div>
          <label htmlFor="subject" className="block text-sm font-medium text-gray-700 mb-1">
            Subject
          </label>
          <select
            id="subject"
            className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
          >
            <option>General Inquiry</option>
            <option>Support</option>
            <option>Feedback</option>
            <option>Other</option>
          </select>
        </div>

        {/* Message */}
        <div>
          <label htmlFor="message" className="block text-sm font-medium text-gray-700 mb-1">
            Message
          </label>
          <textarea
            id="message"
            rows="4"
            className="block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm"
          ></textarea>
        </div>

        {/* Submit */}
        <div>
          <button
            type="submit"
            className="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
          >
            Send Message
          </button>
        </div>
      </form>
    </div>
  );
}
```

---

## Pro Tips

### 1. Create Reusable Input Classes
Extract common styles into a constant or component:

```jsx
const inputClasses = "block w-full rounded-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-400 focus:border-indigo-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 shadow-sm";

<input type="email" className={inputClasses} />
```

### 2. Use Consistent Spacing
- `space-y-4` - 16px spacing between form fields
- `space-y-6` - 24px spacing for section separators
- `mb-1` or `mb-2` - Label to input spacing

### 3. Always Style Focus States
For accessibility, always provide clear focus indicators:
```jsx
focus:outline-none focus:ring-2 focus:ring-indigo-500
```

### 4. Add Transitions
Smooth hover/focus effects improve UX:
```jsx
transition-colors duration-200
```

### 5. Consider Color Schemes
Choose consistent colors:
- **Primary**: `indigo-600`, `indigo-700`
- **Success**: `green-600`, `green-700`
- **Error**: `red-600`, `red-700`
- **Warning**: `yellow-600`, `yellow-700`
- **Neutral**: `gray-600`, `gray-700`

### 6. Responsive Design
Use responsive utilities:
```jsx
<div className="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
  {/* form fields */}
</div>
```

### 7. Dark Mode Support
Add dark mode variants if needed:
```jsx
className="... dark:bg-gray-800 dark:text-white dark:border-gray-600"
```

---

## Color Reference

### Common Tailwind Colors for Forms

**Borders:**
- Default: `border-gray-300`
- Focus: `border-indigo-500`
- Error: `border-red-300`
- Success: `border-green-300`

**Text:**
- Primary: `text-gray-900`
- Labels: `text-gray-700`
- Placeholder: `text-gray-400`
- Helper: `text-gray-500`
- Error: `text-red-600`
- Success: `text-green-600`

**Backgrounds:**
- White: `bg-white`
- Light: `bg-gray-50`
- Disabled: `bg-gray-100`
- Primary Button: `bg-indigo-600`
- Primary Hover: `bg-indigo-700`

**Focus Rings:**
- Default: `focus:ring-indigo-500`
- Error: `focus:ring-red-500`
- Success: `focus:ring-green-500`

---

## Resources

- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Tailwind CSS Forms Examples](https://tailwindui.com/components/application-ui/forms)
- Your working examples: 
  - `/src/components/Login.jsx`
  - `/src/components/Register.jsx`

---

**Created:** October 21, 2025  
**Project:** tailwindcss-form  
**Tailwind Version:** 4.1.15
