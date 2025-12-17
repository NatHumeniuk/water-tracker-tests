# FR-WELCOME: Welcome Page Component

## 1. Overview

**Requirement ID: FR-WELCOME-001**

Priority: High

Description:

The WelcomePage is a public-facing page intended for unauthenticated users.
Its purpose is to present the core value of the Water Tracker application and encourage user registration.

- The WelcomePage shall be rendered at the /welcome route.
- The WelcomePage shall be accessible only to unauthenticated users.
- If an authenticated user attempts to access /welcome, the user shall be redirected to the HomePage (/home).

Acceptance Criteria:

1.

- Given the user is not authenticated
- When the user navigates to /welcome
- Then the WelcomePage is displayed

2.

- Given the user is authenticated
- When the user navigates to /welcome
- Then the user is redirected to the HomePage

## 2. WelcomePage Structure and Layout (For Unauthenticated Users)

**Requirement ID: FR-WELCOME-002**

Priority: High

Description:

The WelcomePage shall contain two main containers:

- WaterConsumptionTracker - Hero section with value proposition and CTA
- WhyDrinkWater - Educational content about water consumption benefits

Layout Rules:

- Sections must appear in the specified order on all breakpoints
- Both sections must be visible without authentication
- The overall page must follow the design layout specified in design assets

![Welcome Page](../images/welcome-page/welcome-page.png)

Acceptance Criteria:

- Given the WelcomePage is loaded
- When the page is rendered
- Then both main containers are displayed in the correct order

### 2.1 WaterConsumptionTracker Component

**Requirement ID: FR-WELCOME-002.1**

Priority: High

Description:

The WaterConsumptionTracker is a hero section component that showcases the application's key features and primary call-to-action for user registration.

WaterConsumptionTracker shall contain the following elements:

1. Heading:

- Text value: Water consumption tracker

2. Subheading

- Text value: Record daily water intake and track

3. Tracker Benefits block contains three unordered list items:

- Icon + text: Habit drive
- Icon + text: View statistics
- Icon + text: Personal rate setting

4. Call-to-Action Button:

- Button text: Try tracker

Acceptance Criteria:

- Given the user is unauthenticated
- And the user navigates to the Welcome Page (route: /welcome)
- When the page loads completely
- Then the heading "Water consumption tracker" is displayed
- And the subheading "Record daily water intake and track" is displayed
- And the Tracker Benefits block is displayed
- And all three benefit items are visible with icons and text:
  - "Habit drive" with icon
  - "View statistics" with icon
  - "Personal rate setting" with icon
- And the "Try tracker" CTA button is displayed
- And all elements are properly styled according to design specifications

### 2.2 TryTracker Button Behavior

**Requirement ID: FR-WELCOME-002.2**

Priority: High

Description:

The "Try tracker" button serves as the primary call-to-action, directing users to the registration page.

Click Interaction:

When the user clicks the "Try tracker" button:

- The user shall be redirected to the Sign Up Page (route: /signup)
- The SignUpPage component shall be rendered

Acceptance Criteria:

- Given the user is on the WelcomePage
- When the user clicks the Try tracker button
- Then the SignupPage is displayed at the route: /signup

### 2.3 WhyDrinkWater Component

**Requirement ID: FR-WELCOME-002.3**

Priority: High

Description:

The WhyDrinkWater component provides educational content about the health benefits of proper water consumption, supporting the application's value proposition

The WhyDrinkWater component shall contain the following content elements:

1. Heading:

    Text value: Why drink water

2. Unordered list consisting of seven items with the following text values:

   - Supply of nutrients to all organs
   - Providing oxygen to the lungs
   - Maintaining the work of the heart
   - Release of processed substances
   -  Ensuring the stability of the internal environment
   - Maintaining within the normal temperature
   - Maintaining an immune system capable of resisting disease

Acceptance Criteria:

- Given the user is on the WelcomePage
- When the WhyDrinkWater component is rendered
- Then the "Why drink water" heading and 7 information items are displayed
