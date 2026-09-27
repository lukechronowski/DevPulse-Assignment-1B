# Assignment 1B
## DevPulse Cloud Infrastructure SaaS
### Section 1: The Less-than-equal-4-Click User Journey Funnel

- **Starting State:** User sees initial viewport of DevPulse website which contains the navigation bar
with company logo, landmark navigation links, and a high-contrast "Deploy Free Cluster" call-to-action and core value metrics in the hero section all of which are directly visible when initially loading the webpage before the user scrolls.
- **Action 1:** User clicks "Deploy Free Cluster" which takes the user to lead capture/register section.
- **Action 2:** User selects intended tier.
- **Action 3:** User navigates to the workload estimator section and inputs data into two constrained number input fields, one for node count and the other for log throughput, to verify tier compatibility.
- **Action 4:** User returns to the pre-registration form, completes the required fields, and submits the form to request API sandbox provisioning details.
- **Terminal State:** User receives visual confirmation that the pre-registration form was successfully
submitted.

### Section 2: Don Norman Usability & Constraint Audit

| Norman Principle | UI Component / Feature Context | Specific HTML Element or Attribute Used to Enforce Principle |
| --- | --- | --- |
| Signifier | Primary Action (Above the Fold) | The `<a>` element with an `href` attribute creates a clickable link that directs the user to the section relevant to the call to action. |
| Signifier | Recommended Tier Indicator | The `<div>` element with a `class` attribute creates a distinct indicator within the `<article>` to identify the recommended tier from the other tier options. |
| Physical/System Constraint | Workload Estimator: Node Count | The `min` and `max` attributes enforce numerical boundaries without JavaScript. The `type="number"` attribute specifies that the `<input>` accepts numerical input. |
| Physical/System Constraint | Operator Contact Field | The `required` attribute ensures the required field cannot be left blank when the form is submitted. |
| Feedback Loop | Form Submission / Live Anchors | The browser moves to the linked section after a live anchor is clicked, indicating the system accepted the action. Similarly, after form submission, a confirmation message or confirmation page would visually indicate the system accepted the submission. |

### Section 3: Semantic Component & Layout Tree

```
index.html
<body>
|--<header class="site-header">
|   |--<a href="#" class="brand-logo">
|   |--<nav class="nav-menu">
|   |   |--<a href="#features">
|   |   |--<a href="#tier-comparison">
|   |   |--<a href="#workload-estimator">
|   |--<a href="#register" class="btn btn-primary"> (Deploy Free Cluster)
|
|--<main>
|   |--<section id="hero" class="hero-section">
|   |   |--<span class="value-metrics"> (Core Value Metrics)
|   |   |--<h1 class="hero-title">
|   |   |--<p class="hero-subtitle">
|   |   |--<div class="cta-group">
|   |   |   |--<a href="#tier-comparison" class="btn btn-primary"> (Tier Comparison)
|   |   |   |--<a href="#workload-estimator" class="btn btn-secondary"> (Workload Estimator)
|   |
|   |--<section id="features" class="features-section">
|   |   |--<header class="section-header">
|   |   |   |--<h2 class="section-title">
|   |   |   |--<p class="section-subtitle">
|   |   |--<div class="features-grid">
|   |   |   |--<article class="feature-card"> (Latency Tracking)
|   |   |   |--<article class="feature-card"> (Log Aggregation)
|   |   |   |--<article class="feature-card"> (Auto-Remediation)
|   |
|   |--<section id="tier-comparison" class="tier-comparison-section">
|   |   |--<header class="section-header">
|   |   |   |--<h2 class="section-title">
|   |   |   |--<p class="section-subtitle">
|   |   |--<div class="tier-grid">
|   |   |   |--<article class="tier-card"> (Developer)
|   |   |   |--<article class="tier-card featured"> (Pro Cluster)
|   |   |   |   |--<div class="popular-tag"> (Most Popular)
|   |   |   |--<article class="tier-card"> (Enterprise Dedicated)
|   |
|   |-- <section id="workload-estimator" class="workload-estimator-section">
|   |   |-- <div class="form-wrapper">
|   |   |   |-- <header class="section-header">
|   |   |   |   |-- <h2 class="section-title">
|   |   |   |   |-- <p class="section-subtitle">
|   |   |   |-- <form action="#" method="post" class="estimator-form">
|   |   |   |   |-- <div class="form-group">
|   |   |   |   |   |-- <label for="node-count" class="form-label"> (Node Count)
|   |   |   |   |   |-- <input type="number" id="node-count" class="form-control" min max step placeholder>
|   |   |   |   |-- <div class="form-group">
|   |   |   |   |   |-- <label for="log-throughput" class="form-label"> (Log Throughput)
|   |   |   |   |   |-- <input type="number" id="log-throughput" class="form-control" min max step placeholder>
|   |   |   |   |-- <button type="submit" class="btn btn-primary"> (Verify Tier Compatibility)
|   |
|   |-- <section id="register" class="lead-capture-section">
|   |   |-- <div class="form-wrapper">
|   |   |   |-- <header class="section-header">
|   |   |   |   |-- <h2 class="section-title">
|   |   |   |   |-- <p class="section-subtitle">
|   |   |   |-- <form action="#" method="post" class="lead-form">
|   |   |   |   |-- <div class="form-group">
|   |   |   |   |   |-- <label for="name" class="form-label"> (Name)
|   |   |   |   |   |-- <input type="text" name="name" id="name" class="form-control" placeholder="e.g. John Smith" required>
|   |   |   |   |-- <div class="form-group">
|   |   |   |   |   |-- <label for="email" class="form-label"> (Email)
|   |   |   |   |   |-- <input type="email" name="email" id="email" class="form-control" placeholder="abc@xyz.com" required>
|   |   |   |   |-- <div class="form-group">
|   |   |   |   |   |-- <label for="tier-selection" class="form-label"> (Tier Selection)
|   |   |   |   |   |-- <select name="tier-selection" id="tier-selection" class="form-control">
|   |   |   |   |   |   |-- <option value="developer"> (Developer)
|   |   |   |   |   |   |-- <option value="pro-cluster"> (Pro Cluster)
|   |   |   |   |   |   |-- <option value="enterprise-dedicated"> (Enterprise Dedicated)
|   |   |   |   |-- <button type="submit" class="btn btn-primary"> (Request API Sandbox Access)
|
|-- <footer class="site-footer">
|   |-- <p> (© 2026 DevPulse. All rights reserved.)
