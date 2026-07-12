# Solution — Challenge B: AI Programming & UX

## Your Name

**Khushi Singh**

---

# Approach

When I first read the problem statement, I noticed that the dashboard was meant for a rehabilitation platform rather than a general analytics application. Because of that, my primary focus was not just displaying data but presenting it in a way that would actually help someone monitor a patient's recovery over multiple rehabilitation sessions.

Instead of treating the dashboard as a collection of charts and statistics, I tried to think about how a therapist would interact with it during a consultation. A therapist generally wants to answer a few questions quickly:

- How is the patient performing overall?
- Is the patient improving over time?
- Which exercises require additional attention?
- Are there any signs of fatigue or declining performance?
- What actions should be taken next?

These questions shaped the overall structure of the dashboard.

Rather than immediately showing detailed exercise data, I placed the most important information at the very top using summary cards. This allows the user to understand the patient's current condition within a few seconds. Once the overall condition is understood, they can scroll further to inspect individual sessions, view rehabilitation trends and finally review automatically generated recommendations.

The entire application follows a simple top-to-bottom information hierarchy.

1. Patient Information
2. Rehabilitation Summary
3. Session History
4. Progress Analytics
5. AI Recommendations

This ordering mirrors how a therapist would naturally review patient progress.

Although the challenge allowed the use of frameworks like React or Vue, I intentionally decided to keep the project lightweight by implementing everything in a single HTML file using Vanilla JavaScript. Since the application only contains one page, introducing a framework would have increased project complexity without providing significant advantages.

Instead, I focused on writing modular JavaScript classes so that different parts of the application remain independent. Data loading, data processing, recommendation generation and UI rendering are separated logically, making the code easier to understand and maintain.

Another objective was to make the interface feel like an actual clinical application rather than a student project. Small details such as consistent spacing, subtle animations, hover effects, loading states and carefully selected colors contribute to making the dashboard feel polished without becoming visually distracting.

The dashboard automatically reads the provided rehabilitation data, calculates all required statistics, creates visualizations, generates personalized recommendations and presents everything through an interactive interface.

Throughout the project, I tried to balance functionality with simplicity. Every feature included in the dashboard was added because it improves the user's ability to understand rehabilitation progress, rather than simply making the interface look more complex.

---

## Tech Stack

The project has been built entirely using frontend technologies because the challenge mainly focused on data visualization, user experience and interface design.

### HTML5

I used HTML5 to create the overall structure of the dashboard. Since the application only contains a single page, keeping everything inside one HTML file made the project easier to manage and submit.

The HTML is divided into logical sections including:

- Header
- Summary Cards
- Session History
- Analytics Section
- AI Recommendation Panel
- Session Comparison Modal
- Footer

Keeping each section separate made it easier to organize both the styling and the JavaScript logic.

---

### CSS3

Instead of using a CSS framework like Bootstrap or Tailwind, I chose to write all the styling manually.

One reason for this decision was flexibility. Clinical dashboards generally require precise spacing, typography and color choices. Writing custom CSS allowed me to control every part of the layout without fighting predefined framework styles.

The project makes extensive use of modern CSS features including:

- CSS Variables
- CSS Grid
- Flexbox
- Media Queries
- Keyframe Animations
- Transitions
- Shadows
- Border Radius
- Responsive Layouts

CSS Variables became especially useful while implementing the dark mode. Instead of rewriting every individual component, I only needed to update the color variables whenever the theme changed.

Animations were intentionally kept subtle. Since this is a healthcare dashboard, excessive animations could become distracting. Small fade-ins, hover transitions and card animations help make the interface feel responsive while maintaining a professional appearance.

---

### Vanilla JavaScript (ES6)

I decided to use Vanilla JavaScript instead of React or another frontend framework.

Since the challenge only required one page, setting up a framework would have introduced additional configuration, dependencies and project structure without significantly improving the final application.

Using plain JavaScript also helped me better demonstrate my understanding of DOM manipulation, data processing and application logic.

To keep the code organized, I avoided writing everything inside one large script. Instead, I separated the logic into different classes and utility sections.

Some of the major JavaScript components include:

- Configuration Object
- DOM Cache
- Data Processor
- Recommendation Engine
- Chart Rendering
- Theme Management
- PDF Export Logic
- Session Comparison Logic

This modular approach makes the application easier to read and maintain compared to placing all functionality inside a single script.

---

### Chart.js

For the visualization section, I chose Chart.js.

The rehabilitation dataset mainly consists of numerical values collected across multiple sessions. These values are much easier to understand when displayed visually instead of as plain numbers.

Chart.js was a good choice because it provides responsive charts with very little setup while still allowing enough customization to match the overall design of the dashboard.

The application currently includes three different visualizations:

- Accuracy progression over multiple sessions
- Exercise-wise performance comparison
- Fatigue trend analysis

These three charts provide different perspectives on the patient's rehabilitation journey and help identify long-term improvements that may not be immediately obvious from individual session data.

### html2canvas

One of the bonus features mentioned in the challenge was the ability to export the dashboard. Instead of generating a text-based report from scratch, I used **html2canvas** to capture the dashboard exactly as it appears on the screen.

This approach preserves the dashboard layout, charts, colors and formatting, allowing users to save a report that closely matches what they are viewing.

---

### jsPDF

After capturing the dashboard using html2canvas, I used **jsPDF** to convert the generated image into a downloadable PDF.

The integration between these two libraries is straightforward and works well for frontend-only applications where no backend is available to generate reports.

---

### Font Awesome

The dashboard makes use of Font Awesome icons throughout the interface.

Icons help users identify different sections more quickly than relying only on text. For example:

- Session History
- Analytics
- AI Recommendations
- Export
- Theme Toggle
- Patient Information

All use recognizable icons that improve visual scanning without adding unnecessary clutter.

---

### Google Fonts (Inter)

Typography plays an important role in dashboards because users spend long periods reading data.

I selected the **Inter** font because it has excellent readability across different screen sizes and gives the interface a clean, modern appearance. It also works well with numerical values, which are displayed frequently throughout the dashboard.

---

# Design Decisions

While designing the dashboard, I tried to think beyond simply fulfilling the challenge requirements. My goal was to create something that could realistically be used inside a rehabilitation clinic.

Unlike business dashboards that often prioritize dense data visualization, rehabilitation software is used by healthcare professionals who need to understand patient progress quickly without becoming overwhelmed by unnecessary information.

For that reason, I kept the interface simple, consistent and easy to navigate.

---

## Understanding the Target User

The expected users of this dashboard are primarily:

- Rehabilitation Therapists
- Physiotherapists
- Prosthetic Specialists
- Clinical Researchers

Patients may also view the dashboard occasionally to monitor their own progress, but therapists are the primary audience.

This influenced several design decisions throughout the project.

For example, therapists usually review multiple patients throughout the day. They don't want to spend several minutes navigating complicated menus or interpreting confusing charts. Important information should be immediately visible.

Because of this, I designed the interface so that the most valuable information appears before any detailed analysis.

---

## Information Hierarchy

One of the biggest priorities during development was deciding where each piece of information should appear.

Rather than randomly placing charts and cards, every section follows a logical order.

### Header

The first thing users see is the application header.

The header contains:

- Dashboard title
- Patient information
- Theme toggle
- Session comparison
- Export button

These are actions that users may frequently access, so placing them at the top makes them easy to reach without scrolling.

The patient information is always visible, ensuring that therapists know exactly whose rehabilitation data they are reviewing.

---

### Summary Cards

Immediately below the header are four summary cards.

These display:

- Total Sessions
- Average Accuracy
- Current Progress
- EMG Quality

These four metrics were selected because they provide the fastest overview of rehabilitation status.

Instead of making users inspect multiple charts to understand overall performance, these cards summarize the patient's condition within a few seconds.

Each card also uses a unique icon and color to improve recognition.

---

### Session History

After reviewing the summary metrics, therapists often want to inspect individual rehabilitation sessions.

Instead of displaying every exercise immediately, I used expandable session cards.

The collapsed card contains only the most important information:

- Session date
- Duration
- Overall progress
- Session number

When expanded, additional exercise information becomes available.

This approach keeps the interface uncluttered while still allowing users to inspect detailed rehabilitation data whenever necessary.

---

### Progress Analytics

Charts are placed after the session history because users generally understand individual sessions before looking at long-term trends.

Three visualizations are included.

#### Accuracy Over Time

This line chart displays how exercise accuracy changes across rehabilitation sessions.

The chart makes it easy to identify:

- Consistent improvement
- Plateaus
- Sudden drops in performance

without reading individual session values.

---

#### Exercise Performance

This chart compares average performance across different rehabilitation exercises.

Instead of looking through every session manually, therapists can immediately identify which exercises need additional attention.

---

#### Fatigue Analysis

Fatigue is an important rehabilitation indicator that can influence patient performance.

Rather than displaying fatigue values as plain numbers, the chart highlights changes across rehabilitation sessions, making trends much easier to identify.

---

### AI Recommendation Panel

The recommendation section appears after all charts because recommendations depend on previously processed rehabilitation data.

Each recommendation contains:

- Priority Badge
- Icon
- Title
- Description

Recommendations are also color coded.

This allows therapists to quickly distinguish between critical recommendations and general improvement suggestions.

---

## Layout Decisions

The dashboard follows a card-based layout throughout the application.

Cards help divide information into manageable sections and improve readability.

Every major feature has its own card including:

- Summary Metrics
- Charts
- Recommendations
- Session History

Using consistent card styling also creates a predictable user experience.

---

## Color Palette

The dashboard uses colors inspired by healthcare applications rather than bright marketing websites.

Blue is used as the primary color because it is commonly associated with trust, professionalism and healthcare.

Green indicates positive progress or successful rehabilitation.

Yellow is used for warnings that require attention but are not immediately critical.

Red is reserved only for high-priority alerts or poor rehabilitation performance.

Neutral gray backgrounds help important information stand out without overwhelming the user.

---

## Typography

Readability was one of the main priorities throughout development.

Large numerical values are used for important rehabilitation metrics because users should be able to understand the patient's condition at a glance.

Headings are bold enough to separate sections clearly without making the interface feel crowded.

Smaller supporting text provides additional context without competing for attention.

---

## Spacing and White Space

One mistake commonly seen in dashboards is trying to fit too much information into a limited space.

I intentionally added generous spacing between sections.

This improves readability and makes the dashboard feel less overwhelming, especially when large amounts of rehabilitation data are displayed.

Cards also include consistent padding so that content never appears cramped.

---

## Responsiveness

The dashboard has been designed to work across different screen sizes.

Desktop users receive a multi-column layout that utilizes the available screen width efficiently.

On tablets and smaller devices, the layout automatically adjusts.

Summary cards reorganize into smaller grids.

Charts stack vertically.

Buttons become easier to tap.

Text sizes adjust where necessary.

These changes allow the dashboard to remain usable without requiring horizontal scrolling.

Instead of creating separate layouts for each device, responsive media queries dynamically adapt the interface based on screen width.

---

## Animations

Animations were intentionally kept minimal.

Healthcare software should feel responsive without becoming distracting.

Small animations were added only where they improve user experience.

These include:

- Dashboard fade-in
- Card appearance animations
- Hover effects
- Expandable session transitions
- Theme switching
- Modal opening animations

These subtle interactions make the dashboard feel more polished while ensuring that the rehabilitation data remains the primary focus.

---

## Component Reusability

Although the project is contained within a single HTML file, I still tried to organize the code so that components remain reusable.

The same card styling is reused throughout the dashboard.

Buttons share common styles.

Color variables are centralized.

Configuration values are stored separately from application logic.

This makes future modifications easier without requiring changes throughout the entire codebase.

# AI Recommendations

One of the requirements of the challenge was to implement an AI-powered recommendation system. Since the problem statement mentioned that a machine learning model was not necessary, I chose to build a rule-based recommendation engine.

My goal was to make the recommendations feel practical rather than random. Instead of generating generic advice, the system evaluates different rehabilitation metrics and only produces recommendations when certain conditions are met.

The recommendation engine runs automatically after the patient data has been loaded and processed. It examines every rehabilitation session along with overall patient trends before generating personalized suggestions.

This approach keeps the logic transparent and easy to understand. If a therapist reviews the recommendation, they can easily identify which patient metric triggered it.

---

### The 12 Recommendation Rules

The recommendation engine uses 12 rule-based logic to generate personalized insights:

| Rule | Name | Logic | Priority |
|------|------|-------|----------|
| 1 | Accuracy Trend Analysis | If last 3 sessions show no improvement AND avg accuracy < 70% | HIGH |
| 2 | High Performance Encouragement | If exercise accuracy > 80% AND < 92% | MEDIUM |
| 3 | Low Performance Focus | If exercise accuracy < 55% | HIGH |
| 4 | Fatigue Management | If exercise fatigue index > 0.7 | MEDIUM |
| 5 | Excellent Session Celebration | If latest session accuracy > 85% | LOW |
| 6 | Recovery Focus | If latest session fatigue > 0.6 | MEDIUM |
| 7 | EMG Quality Alert | If EMG quality score < 0.6 | HIGH |
| 8 | Progress Tracking | If improvement from first session is 0-15% | LOW |
| 9 | Session Duration Consistency | If latest session < 25min AND 10min below average | MEDIUM |
| 10 | Consecutive Improvement Streak | If accuracy increased for 3+ consecutive sessions | LOW |
| 11 | Session Gap Analysis | If gap between sessions > 5 days | MEDIUM |
| 12 | Exercise Variety | If patient only uses 1-2 exercise types | MEDIUM |

> **Note:** Rules 10-12 are implemented in the code but are not explicitly described in the text above. They were added to cover gaps in patient consistency and exercise diversity.

---

### Recommendation Workflow

The recommendation engine follows a simple workflow.

1. Load patient rehabilitation data.
2. Calculate overall rehabilitation statistics.
3. Analyse every exercise across all sessions.
4. Detect trends in performance.
5. Check predefined conditions.
6. Generate recommendations.
7. Assign a priority level.
8. Display recommendations on the dashboard.

This process happens automatically whenever the dashboard loads.

---

### Performance Analysis

The recommendation engine first analyses rehabilitation performance across all recorded sessions.

Instead of considering only the latest session, it evaluates long-term progress because rehabilitation is generally measured over weeks rather than a single day.

The system looks for patterns such as:

- Continuous improvement
- Declining performance
- Stagnant recovery
- Consistency between sessions
- Sudden changes in rehabilitation metrics

Looking at overall trends provides more meaningful recommendations than reacting to individual values.

---

### Exercise Accuracy

Accuracy is one of the most important rehabilitation indicators.

The dashboard analyses exercise accuracy for every rehabilitation session and compares the results over time.

If an exercise repeatedly produces low accuracy scores, the recommendation engine suggests that additional attention should be given to that exercise.

Similarly, consistently high accuracy may result in recommendations encouraging progression to more advanced exercises.

This prevents the recommendations from being entirely negative and allows the system to recognise successful rehabilitation as well.

---

### Fatigue Monitoring

Fatigue plays an important role during rehabilitation.

High fatigue may indicate that the patient is performing too many repetitions or that recovery time between sessions is insufficient.

The recommendation engine analyses fatigue values across different exercises and sessions.

If fatigue levels remain consistently high, recommendations are generated encouraging therapists to review exercise intensity or scheduling.

On the other hand, decreasing fatigue across multiple sessions is interpreted as a positive recovery trend.

---

### EMG Signal Quality

The provided dataset includes an EMG quality score for every rehabilitation session.

EMG quality directly affects how accurately muscle activity is interpreted by the rehabilitation system.

Lower EMG quality scores may indicate poor sensor placement or weak signal acquisition.

When these values fall below expected levels, the dashboard recommends reviewing sensor placement before continuing rehabilitation.

Monitoring EMG quality separately prevents inaccurate rehabilitation data from influencing future therapy decisions.

---

### Overall Progress

The recommendation engine also monitors the patient's overall rehabilitation progress.

Instead of looking only at exercise performance, it evaluates whether the patient is making consistent progress throughout the rehabilitation program.

If progress continues to increase steadily across sessions, the dashboard generates positive reinforcement.

If progress remains unchanged for several sessions, recommendations encourage therapists to reassess the rehabilitation plan.

This helps identify situations where patients may have reached a plateau.

---

### Response Time Analysis

Average response time is another useful rehabilitation metric.

Lower response times generally indicate improved muscle coordination and faster patient reactions.

The dashboard compares response times across rehabilitation sessions to identify improvements or slowdowns.

Large increases in response time may indicate fatigue or reduced motor control and therefore contribute to rehabilitation recommendations.

---

### Exercise Comparison

Some rehabilitation exercises naturally perform better than others.

Instead of analysing exercises individually, the recommendation engine compares average performance between exercise types.

This comparison helps identify exercises that consistently produce lower accuracy or higher fatigue.

Therapists can then decide whether additional practice or modified rehabilitation strategies are required.

---

### Priority Levels

Not every recommendation requires immediate attention.

To make the dashboard easier to interpret, recommendations are grouped into three priority levels.

#### High Priority

These recommendations indicate issues that should be reviewed as soon as possible.

Examples include:

- Very low exercise accuracy
- High fatigue values
- Poor EMG quality
- Declining rehabilitation progress

These recommendations appear with stronger visual emphasis to immediately attract attention.

---

#### Medium Priority

These recommendations represent situations that should be monitored but are not immediately critical.

Examples include:

- Moderate fatigue
- Small decrease in exercise performance
- Inconsistent rehabilitation progress
- Exercises requiring additional practice

Medium-priority recommendations encourage gradual adjustments rather than urgent intervention.

---

#### Low Priority

Low-priority recommendations are generally positive.

Examples include:

- Consistent improvement
- Stable rehabilitation progress
- High exercise accuracy
- Good EMG quality

Displaying positive feedback helps recognise patient achievements rather than only highlighting problems.

---

### Why a Rule-Based System?

Although more advanced AI models could have been used, I felt that a rule-based approach was more appropriate for this prototype.

There were three reasons for this decision.

First, the challenge explicitly mentioned that machine learning was optional.

Second, the dataset provided was relatively small, making it difficult to justify training a reliable prediction model.

Finally, rule-based recommendations are transparent.

Every recommendation can be traced back to specific rehabilitation metrics, making the system easier for therapists to trust and understand.

For a clinical application, explainability is often just as important as prediction accuracy.

# Accessibility

Accessibility was considered throughout the design process because rehabilitation software may be used by people with different levels of technical experience.

The objective was to create an interface that remains easy to understand regardless of the user's familiarity with technology.

---

## Responsive Design

The dashboard has been designed to work across desktops, laptops and tablets.

Instead of creating separate layouts for different devices, responsive media queries automatically adjust the interface.

Depending on the available screen width:

- Cards reorganise into smaller grids.
- Charts resize automatically.
- Navigation controls remain accessible.
- Text scales appropriately.
- Buttons become easier to interact with.

This allows the dashboard to remain functional without sacrificing readability.

---

## Readability

Large amounts of numerical rehabilitation data can quickly become overwhelming if presented poorly.

To improve readability:

- Important numbers are displayed using larger font sizes.
- Section headings clearly separate different areas of the dashboard.
- Supporting information uses smaller secondary text.
- Consistent spacing improves visual scanning.

The goal was to reduce the amount of effort required to locate important rehabilitation information.

---

## Colour Contrast

The chosen colour palette maintains clear contrast between text and background elements.

Primary rehabilitation metrics are easy to distinguish without relying solely on colour.

Priority badges combine both colours and labels so that users can understand recommendation importance even if colour perception is limited.

---

## Icons and Labels

Icons are used throughout the interface to improve recognition.

However, icons are never displayed without accompanying text.

Every important action still includes a readable label, ensuring that users are not required to interpret symbols alone.

---

## Interactive Feedback

Every interactive element provides visual feedback.

Buttons change appearance when hovered.

Session cards indicate whether they are expanded or collapsed.

Theme switching updates immediately.

Comparison selections are visually highlighted.

Providing immediate feedback helps users understand that their actions have been recognised.

---

## Dark Mode

The application includes a complete dark mode.

Instead of simply inverting colours, a separate set of CSS variables controls the dashboard theme.

This ensures that charts, cards, text and interactive components remain readable in both themes.

Users can switch between light mode and dark mode without refreshing the page.

---

## Consistency

Consistency is one of the most important aspects of accessibility.

Throughout the dashboard I maintained consistent:

- Card spacing
- Border radius
- Font sizes
- Button styles
- Icon placement
- Section layouts
- Colour usage

Keeping these design elements consistent reduces cognitive load and makes the interface easier to learn for first-time users.

# How to Run

The project does not require any build tools or package installation. Since it is built using HTML, CSS and JavaScript, the only requirement is to serve the project through a local web server so that the JSON data can be loaded correctly using the Fetch API.

### Step 1: Clone the Repository

```bash
git clone <repository-url>
```

---

### Step 2: Open the Project Directory

```bash
cd <repository-folder>
```

---

### Step 3: (Live Server via npm)


I used the `live-server` command to run the project locally. Here's exactly what I did:

```bash
# Navigate to the project root
cd kawatek-intern-challenge

# Run live-server on the challenge-b folder
live-server challenges/challenge-b/
```
The dashboard opened automatically in my browser at:127.0.0.1:8080
This is the recommended way to run the project, as it provides live reloading and works seamlessly with the Fetch API.

---

### Notes

The project should be served through a local server because the application loads JSON data using the Fetch API. Opening the HTML file directly in the browser may prevent the data from loading due to browser security restrictions.

No additional configuration or installation is required.

---

# Screenshots

The following screenshots have been included with the submission to demonstrate the completed implementation:
drive link :https://drive.google.com/file/d/1lgVE9I7kwBWyl9Xd2J9zTGNUeVCv1mJu/view?usp=sharing


## Dashboard Overview

Displays the complete rehabilitation dashboard including:

- Patient information
- Summary metrics
- Charts
- Session history
- AI recommendations

---

## Summary Cards

Displays the four key rehabilitation metrics:

- Total Sessions
- Average Accuracy
- Current Progress
- EMG Quality Score

---

## Session History

Shows expandable rehabilitation sessions with detailed exercise information including:

- Repetitions
- Accuracy
- Response Time
- Fatigue Index
- Duration

---

## Analytics Dashboard

Includes all three required visualizations:

- Progress Over Time
- Exercise Performance Comparison
- Fatigue Trend Analysis

---

## AI Recommendation Panel

Displays automatically generated recommendations together with their corresponding priority levels.

---

## Dark Mode

Demonstrates the complete dark theme implementation while preserving readability and chart visibility.

---

## Session Comparison

Shows the side-by-side comparison feature for analysing rehabilitation progress across different sessions.

---

## Export Feature

Illustrates the generated PDF report that can be downloaded directly from the dashboard.

---

# Bonus Features Implemented

The following bonus features from the challenge have been implemented:

| Feature | Status | Description |
|---------|--------|-------------|
| **Dark/Light Mode Toggle** | ✅ Implemented | CSS variables toggle with localStorage persistence |
| **Session Comparison** | ✅ Implemented | Select 2 sessions → side-by-side comparison with conclusions |
| **PDF Export** | ✅ Implemented | Captures dashboard using html2canvas + jsPDF |

---

### Dark Mode

A complete dark theme has been implemented using CSS variables.

Rather than maintaining two separate stylesheets, the application dynamically changes theme variables whenever the user switches between light mode and dark mode.

This keeps the implementation simple while ensuring every component updates consistently.

The selected theme is also remembered during the current session, allowing users to continue working without repeatedly changing appearance settings.

---

### Session Comparison

One of the additional features I implemented was session comparison.

Users can select two rehabilitation sessions and compare their performance side by side.

The comparison includes:

- Overall Progress
- EMG Quality
- Session Duration
- Exercise Accuracy
- Fatigue Levels
- Response Times

This feature makes it easier to observe rehabilitation improvements between different stages of recovery without manually switching between multiple session cards.

---

### PDF Export

The dashboard can be exported as a PDF document.

Instead of generating a plain text report, the application captures the current dashboard layout and converts it into a downloadable PDF.

This allows therapists to save rehabilitation summaries for documentation or share reports with patients and other healthcare professionals.

---

## Interactive Charts

Although charts were part of the required functionality, additional effort was made to improve their presentation.

The charts automatically resize on different screen sizes and clearly highlight rehabilitation trends without overwhelming the user with unnecessary visual elements.

Animations were kept subtle so that they improve the experience without distracting from the displayed information.

---

## Responsive Layout

The application has been tested across different screen sizes to ensure usability on desktops and tablets.

The layout automatically adjusts by reorganising cards, resizing charts and stacking components where necessary.

No horizontal scrolling is required during normal use.

---

## Smooth User Experience

Several small improvements were added throughout the interface to make the dashboard feel more polished.

These include:

- Loading animations while data is being processed.
- Expandable session cards with smooth transitions.
- Hover effects on interactive elements.
- Consistent spacing across all sections.
- Clearly differentiated recommendation priorities.
- Smooth theme switching.
- Organized information hierarchy.

These details may seem small individually, but together they make the dashboard more intuitive to use.

---

# Challenges Faced

Implementing the recommendation engine also required balancing simplicity with usefulness. Since the challenge did not require machine learning, I focused on creating clear rule-based recommendations that respond to actual rehabilitation metrics rather than generating generic advice.

Finally, ensuring that all components remained responsive while maintaining a clean layout required careful use of CSS Grid, Flexbox and media queries.

---

# Future Improvements

If this project were to be developed further, several additional features could be incorporated.

Some possible improvements include:

- User authentication for therapists and patients.
- Integration with a backend database for storing rehabilitation history.
- Real-time rehabilitation monitoring using WebSockets.
- Machine learning models capable of predicting rehabilitation outcomes.
- Customisable rehabilitation goals.
- Advanced filtering and search for rehabilitation sessions.
- Multi-patient management dashboard.
- Cloud-based report generation.
- Notification system for rehabilitation milestones.
- Integration with wearable rehabilitation devices.

These additions would move the application closer to a production-ready rehabilitation management platform.

---

# Conclusion

This project was an opportunity to apply frontend development skills to a practical healthcare scenario.

Instead of focusing only on meeting the functional requirements, I aimed to create a dashboard that presents rehabilitation data in a clear and meaningful way. Throughout the development process, I paid attention to layout, responsiveness, accessibility and usability so that the interface would feel like a realistic clinical application rather than a simple prototype.

The final dashboard successfully loads and processes the provided rehabilitation dataset, visualises patient progress using interactive charts, generates rule-based recommendations, supports responsive layouts and includes additional features such as dark mode, PDF export and session comparison.

Overall, the project allowed me to combine data visualisation, frontend development and user interface design into a single application while keeping the implementation lightweight, maintainable and easy to use.

