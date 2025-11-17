# Booking Widget - Fixed Duration Services

Online booking widget for fixed duration services using Bookla API. Users can select a date, time, and resource, then fill out a booking form. The component supports guest mode, custom form fields, and terms and conditions.

## Preview

![Booking Widget](./preview.jpg)

## Installation

### Step 1: Open Your Framer Project

1. Launch **Framer Desktop** or open your project in **Framer Web**
2. Navigate to your project where you want to add the booking widget

### Step 2: Create a New Code Component

1. In Framer, click the **"+"** button in the components panel (or press `Cmd/Ctrl + K`)
2. Select **"Code Component"** from the menu
3. Name it `FixedBookingWidget` (or any name you prefer)
4. Click **"Create"**

### Step 3: Copy and Paste the Component Code

1. Open the [`component.tsx`](./component.tsx) file from this repository
2. **Select all** the code (`Cmd/Ctrl + A`) and **copy** it (`Cmd/Ctrl + C`)
3. In Framer, you should now see a code editor with a basic component template
4. **Delete all** the existing template code
5. **Paste** the copied code into the editor
6. The component should automatically save (or press `Cmd/Ctrl + S`)

### Step 4: Add Required Dependencies

The component uses external packages. You may need to install them:

1. In Framer, check if there's a **package.json** or dependency management section
2. If using npm/yarn, install these packages:
   ```bash
   npm install uuid
   ```
3. The component also uses:
   - `lucide-react` (for icons) - may need to be installed
   - `@bookla-app/react-client-sdk` (loaded via CDN in the component)

**Note:** If Framer shows import errors, you may need to:
- Install packages via Framer's package manager (if available)
- Or ensure the CDN imports are working properly

### Step 5: Add the Component to Your Canvas

1. In the **Components** panel, find your `FixedBookingWidget` component
2. **Drag and drop** it onto your canvas
3. The component should appear with default styling

### Step 6: Configure Bookla API Connection

1. **Sign up** at [Bookla.com](https://bookla.com) if you haven't already
2. Get your **API Key** and **Company ID** from your Bookla dashboard
3. Select the component on your canvas
4. In the **Properties Panel** (right side), find the **"Bookla"** section
5. Configure:
   - **API region**: Choose `'us'` or `'eu'` based on your Bookla account location
   - **API Key**: Paste your Bookla API key
   - **Company ID**: Paste your Bookla company ID
6. Set the **Service ID** to the ID of the "fixed" service you want to book

### Step 7: Customize the Component

Use the **Properties Panel** to customize:
- Colors, fonts, and styling
- Text labels and messages
- Form fields
- Popup settings (see below)

### Troubleshooting

**If the component doesn't appear:**
- Check the Framer console for errors (View → Console)
- Ensure all dependencies are properly installed
- Verify the code was pasted completely

**If API calls fail:**
- Double-check your API key and Company ID
- Verify your Service ID is correct
- Check that your Bookla account is active
- Ensure your API region matches your account region

**If styling looks off:**
- Check that all color properties are set correctly
- Verify font family is available
- Ensure border radius values are valid

## Properties

This component provides extensive customization options through Framer's property controls. All properties are optional unless marked as required.

### Basic Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `size` | `'sm' \| 'md' \| 'lg'` | `'md'` | Component size variant |
| `backgroundColor` | `Color` | `'white'` | Background color of the component |
| `primaryColor` | `Color` | `'black'` | Primary brand color |
| `secondaryColor` | `Color` | `'#666'` | Secondary text color |
| `fontFamily` | `String` | `'Inter'` | Font family for text elements |
| `locale` | `String` | `'en-US'` | Locale for date/time formatting |
| `localTime` | `Boolean` | `true` | Use local timezone for time display |
| `guestMode` | `Boolean` | `true` | Allow booking without user login |

### Bookla API Configuration

| Property           | Type | Default | Required | Description |
|--------------------|------|---------|----------|-------------|
| `bookla.apiKey`    | `String` | `''` | ✅ | Your Bookla API key |
| `bookla.companyID` | `String` | `''` | ✅ | Your Bookla company ID |
| `bookla.apiRegion` | `'us' \| 'eu'` | `'us'` | - | API region (U.S. or Europe) |
| `serviceID`        | `String` | `''` | ✅ | Service ID to book |

### Pre-selection Options

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `selectedDate` | `Date` | - | Pre-select a specific date |
| `selectedResourceID` | `String` | `''` | Pre-select a specific resource |

### Item Styling

Customize the appearance of selectable items (dates, times, etc.):

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `item.bgColor` | `Color` | `'#f5f5f5'` | Background color of items |
| `item.selectColor` | `Color` | `'black'` | Brand color for selected items |
| `item.selectedTextColor` | `Color` | `'white'` | Text color on selected items |
| `item.selectedSecondaryTextColor` | `Color` | `'white'` | Secondary text color on selected items |
| `item.borderRadius` | `BorderRadius` | `'8px'` | Border radius for items |

### Button Styling

Customize the main action buttons:

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `button.bgColor` | `Color` | `'black'` | Button background color |
| `button.textColor` | `Color` | `'white'` | Button text color |
| `button.borderRadius` | `BorderRadius` | `'32px'` | Button border radius |

### Block Layout

Configure the layout and spacing of content blocks:

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `blocks.gap` | `Number` | `8` | Gap between blocks (px) |
| `blocks.padding` | `Padding` | `'20px'` | Internal padding of blocks |
| `blocks.border` | `Border` | `2px solid #F5F5F5` | Border styling for blocks |
| `blocks.borderRadius` | `BorderRadius` | `'16px'` | Border radius for blocks |

### Date Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `datesCount.min` | `Number` | `3` | Minimum number of dates to show |
| `datesCount.max` | `Number` | `7` | Maximum number of dates to show |

### Resource Picker

Configure the resource selection functionality:

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `resourcePicker.visible` | `Boolean` | `false` | Show/hide resource selector |
| `resourcePicker.selectResourceText` | `String` | `'Select resource'` | Text for resource selection prompt |
| `resourcePicker.anyResourceText` | `String` | `'Any resource'` | Text for "any resource" option |

### Guest Mode Configuration

*Only visible when `guestMode` is enabled*

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `guestModeTexts.title` | `String` | `'Client\'s data'` | Guest form section title |
| `guestModeTexts.subtitle` | `String` | `'Please fill the form below'` | Guest form section subtitle |
| `guestModeTexts.firstName` | `String` | `'First Name'` | First name field label |
| `guestModeTexts.lastName` | `String` | `'Last Name'` | Last name field label |
| `guestModeTexts.email` | `String` | `'Email'` | Email field label |

### Custom Form Fields

Configure additional form fields for booking:

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `customForm.formTitle` | `String` | `'Additional data'` | Custom form section title |
| `customForm.formSubtitle` | `String` | `'Please enter fields below'` | Custom form section subtitle |
| `customForm.fields` | `Array` | `[]` | Array of custom form field objects |

#### Custom Form Field Object

Each field in the `customForm.fields` array has these properties:

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `labelText` | `String` | `''` | Field label text |
| `type` | `'text' \| 'textarea' \| 'number' \| 'multiselect' \| 'select' \| 'phone' \| 'url'` | `'text'` | Input field type |
| `options` | `String` | `''` | Comma-separated options (for select/multiselect) |
| `placeholderText` | `String` | `'Enter value'` | Placeholder text |
| `inputWidth` | `'auto / span 1' \| 'auto / span 2'` | `'auto / span 2'` | Field width (Half or Full) |
| `required` | `Boolean` | `true` | Whether field is required |
| `errorText` | `String` | `'This field is required'` | Error message for validation |

### Terms and Conditions

*Only visible when `showTerms` is enabled*

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `showTerms` | `Boolean` | `false` | Show/hide terms checkbox |
| `terms.text` | `String` | `'I agree to the'` | Terms agreement text |
| `terms.highlightedText` | `String` | `'Terms and Conditions'` | Clickable terms link text |
| `terms.termsLink` | `String` | `'https://example.com/terms'` | URL for terms and conditions |

### User Interface Text

Customize all user-facing text:

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `texts.noTimes` | `String` | `'Sorry, but no times are available for this date'` | Message when no time slots available |
| `texts.continue` | `String` | `'Continue'` | Continue button text |
| `texts.makeBooking` | `String` | `'Make booking'` | Final booking button text |
| `texts.loginToBook` | `String` | `'Please login to book'` | Login required button text |

### Navigation Routes

Configure where users are redirected after booking (only used when `showPopup` is `false`):

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `routes.confirmed` | `Link` | `'/'` | Page to redirect to for confirmed bookings |
| `routes.pending` | `Link` | `'/'` | Page to redirect to for pending bookings |

### Popup Settings

**NEW FEATURE:** Instead of redirecting to a new page after booking, you can show a customizable popup modal.

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `showPopup` | `Boolean` | `false` | Enable popup instead of redirecting after booking |
| `popup.message` | `String` | `'Booking confirmed! Thank you for your reservation.'` | Custom message displayed in the popup |
| `popup.buttonText` | `String` | `'Close'` | Text for the popup button |
| `popup.buttonAction` | `Link` | `''` | Optional: Route to navigate to when button is clicked. Leave empty to just close the popup |

**How it works:**
- When `showPopup` is `true`, after a successful booking, a modal popup appears instead of redirecting
- The popup uses the same styling as the widget (colors, fonts, border radius) for consistency
- Users can click outside the popup or use the button to close it
- If `popup.buttonAction` is set, clicking the button will navigate to that route
- If `popup.buttonAction` is empty, clicking the button just closes the popup and resets the form

## Quick Usage Examples

### Example 1: Basic Setup with Redirect

1. Add the component to your canvas
2. Configure Bookla API credentials
3. Set `showPopup` to `false` (default)
4. Configure `routes.confirmed` and `routes.pending` to your success pages
5. Users will be redirected after booking

### Example 2: Using the Popup Feature

1. Add the component to your canvas
2. Configure Bookla API credentials
3. Set `showPopup` to `true`
4. Customize `popup.message` (e.g., "Thank you! Your booking is confirmed.")
5. Customize `popup.buttonText` (e.g., "Got it" or "View Booking")
6. Optionally set `popup.buttonAction` to navigate to a specific page when the button is clicked
7. Users will see a popup after booking instead of being redirected

### Example 3: Custom Styling

1. Match your brand colors:
   - Set `primaryColor` to your brand color
   - Set `item.selectColor` to your accent color
   - Set `button.bgColor` to match your CTA button color
2. Match your typography:
   - Set `fontFamily` to your brand font (e.g., "Inter", "Poppins")
3. Adjust spacing:
   - Increase `blocks.gap` for more space between sections
   - Adjust `blocks.padding` for internal spacing

## Styling Tips

- Use `primaryColor` and `item.selectColor` for consistent branding
- Adjust `blocks.gap` and `blocks.padding` for better spacing
- Customize `fontFamily` to match your brand typography
- Set `item.borderRadius` and `button.borderRadius` for consistent corner styling
- Set `locale` to match your target audience's language and region to ensure proper date, number, and currency formatting
- The popup automatically inherits your widget's styling for a cohesive look