# Unveil App Design System

This design system document provides guidelines for creating consistent user interfaces for the Unveil App, ensuring visual cohesion and proper functionality across all screens.

## Table of Contents
1. [Core Principles](#core-principles)
2. [Color Palette](#color-palette)
3. [Typography](#typography)
4. [Layout Guidelines](#layout-guidelines)
5. [Components](#components)
6. [Screen Archetypes](#screen-archetypes)

## Core Principles

- **Privacy-Focused**: UI elements should communicate security and trust
- **Mobile-First**: All screens optimized for mobile with max-width of 430px
- **Accessibility**: High contrast ratios and readable font sizes
- **Consistent Navigation**: Bottom navbar consistent across all screens
- **Clean & Modern**: White backgrounds, rounded corners, subtle shadows

## Color Palette

### Primary Colors
- **Primary Purple**: `#8a3ffc` - Used for primary actions, buttons, and highlights
- **Light Purple**: `#f0e6ff` - Used for hover states and secondary highlights
- **Gradient Purple**: `linear-gradient(135deg, #6366f1, #a855f7)` - Used for cards and CTAs

### Secondary Colors
- **Background**: `#f8f9fa` - Main background color
- **White**: `#ffffff` - Card backgrounds, contrasting elements
- **Text Primary**: `#333333` - Primary text color
- **Text Secondary**: `#666666` - Secondary text color
- **Text Tertiary**: `#999999` - Muted text, timestamps

### Semantic Colors
- **Success/Low Risk**: `#4caf50` / `#28a745` / `#4ade80`
- **Warning/Medium Risk**: `#ff9800` / `#ffc107`
- **Danger/High Risk**: `#f44336` / `#dc3545` / `#f87171`

## Typography

### Font Family
- Primary font: `'Inter', sans-serif` (index.html)
- Alternative: `'Segoe UI', Tahoma, Geneva, Verdana, sans-serif` (chat.html)

### Font Sizes
- **Extra Large (h1)**: `24px` - Page titles
- **Large (h2)**: `20px` - Section titles, card headers
- **Medium (h3)**: `18px` - Component headers
- **Regular**: `16px` - Standard text
- **Small**: `14px` - Secondary text, descriptions
- **Extra Small**: `12px` - Timestamps, labels
- **Tiny**: `11px` - Badges, indicators

### Font Weights
- **Bold**: `700` - Headings, important text
- **Semi-Bold**: `600` - Subheadings, emphasized text
- **Medium**: `500` - Buttons, navigation
- **Regular**: `400` - Body text

## Layout Guidelines

### Container Structure
- **Maximum Width**: `430px`
- **Page Padding**: `15px` to `20px`
- **Content Area**: Allow for bottom padding (`90px`) to accommodate the floating navbar

### Spacing System
- **Extra Small**: `5px` - Minimal spacing between related elements
- **Small**: `10px` - Standard spacing between related elements
- **Medium**: `15px` - Spacing between components
- **Large**: `20px` - Section spacing
- **Extra Large**: `30px` - Major section divisions

### Grid System
- **Flexible Layout**: Use flexbox for responsive layouts
- **Card Grid**: Cards should be full width with consistent margin/padding

## Components

### Status Bar
```html
<div class="status-bar">
    <div class="time">9:41</div>
    <div class="status-icons">
        <i class="fas fa-wifi"></i>
        <i class="fas fa-signal"></i>
        <i class="fas fa-battery-full"></i>
    </div>
</div>
```

### Header
```html
<div class="header">
    <div class="greeting">
        <h1>Hi, [Username] <span>👋</span></h1>
        <p>Unveil App: Relationship insights with privacy</p>
    </div>
    <div class="notification-icon">
        <i class="fas fa-bell"></i>
        <span class="notification-badge">3</span>
    </div>
</div>
```

### Cards

#### Primary Card (Insights Card)
```html
<div class="insights-card">
    <div class="insights-header">
        <div>
            <div class="insights-label">PERSONALIZED ANALYSIS</div>
            <div class="insights-title">Communication Insights</div>
        </div>
        <div class="insights-date">June 2, 2025</div>
    </div>
    
    <div class="insights-recommendation">
        <div class="recommendation-title">
            <i class="fas fa-lightbulb"></i>
            <span>KEY INSIGHT</span>
        </div>
        <div class="recommendation-text">
            <strong>Assertive Communication:</strong> Content here...
        </div>
    </div>
</div>
```

### Standalone Components

#### Upload Section with iOS-Style Info
```html
<div class="upload-section">
    <div class="section-header">
        <h3 class="upload-section-title">ANALYZE YOUR CONVERSATIONS</h3>
        <button class="info-button" aria-label="Information">
            <i class="fas fa-info-circle"></i>
        </button>
    </div>
    <div id="infoModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>How to Analyze Conversations</h3>
                <button class="close-button">&times;</button>
            </div>
            <div class="modal-body">
                <p>Upload audio or video from your chat history to get more personalized insights. Learn how to export your chat history by watching the <a href="tutorial-link" class="tutorial-link">tutorial video</a>.</p>
            </div>
        </div>
    </div>
    <button class="upload-card-button" id="newUploadBtn">
        <i class="fas fa-plus"></i>
        Upload Chat History
    </button>
</div>
```

#### Required JavaScript
```javascript
// Modal functionality
document.addEventListener('DOMContentLoaded', function() {
    const infoButton = document.querySelector('.info-button');
    const modal = document.getElementById('infoModal');
    const closeButton = document.querySelector('.close-button');
    
    if (infoButton && modal) {
        // Show modal when info button is clicked
        infoButton.addEventListener('click', function() {
            modal.style.display = 'flex';
        });
        
        // Close modal when close button is clicked
        closeButton.addEventListener('click', function() {
            modal.style.display = 'none';
        });
        
        // Close modal when clicking outside the modal content
        window.addEventListener('click', function(event) {
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        });
    }
});
```

#### Content Card (Analysis Card)
```html
<div class="analysis-card">
    <div class="card-main-content">
        <div class="analysis-header">
            <div class="analysis-avatar">
                <img src="profile-image-url" alt="Contact Name">
            </div>
            <div class="analysis-info">
                <div class="analysis-name">
                    Contact Name
                </div>
                <div class="analysis-time">Time ago</div>
            </div>
            <span class="analysis-risk risk-[level]">Risk Level</span>
        </div>
        <div class="analysis-content">
            <h3 class="analysis-pattern-title">Pattern Title</h3>
            <div class="analysis-tags">
                <!-- Tags content -->
            </div>
        </div>
    </div>
    <div class="chat-section">
        <button class="chat-icon" data-contact="Contact Name">
            <i class="fas fa-comment-alt"></i>
        </button>
    </div>
</div>
```

### Buttons

#### Primary Button
```html
<button class="upload-card-button">
    <i class="fas fa-plus"></i>
    Button Text
</button>
```

#### Icon Button (Chat Icon)
```html
<button class="chat-icon" data-contact="Contact Name">
    <i class="fas fa-comment-alt"></i>
</button>
```

#### Info Icon with Tooltip
```html
<div class="info-icon">
    <i class="fas fa-info"></i>
    <div class="info-tooltip">
        Tooltip content here
    </div>
</div>
```

### Bottom Navigation Bar
```html
<div class="navigation">
    <a href="#" class="nav-item active">
        <div class="nav-icon"><i class="fas fa-home"></i></div>
        <div>Home</div>
    </a>
    <a href="#" class="nav-item">
        <div class="nav-icon"><i class="fas fa-chart-line"></i></div>
        <div>Insights</div>
    </a>
    <a href="#" class="nav-item">
        <div class="nav-icon"><i class="fas fa-comment-alt"></i></div>
        <div>Chat</div>
    </a>
    <a href="#" class="nav-item">
        <div class="nav-icon"><i class="fas fa-user"></i></div>
        <div>Profile</div>
    </a>
</div>
```

### Messages (Chat)
```html
<div class="message ai-message">
    AI message content here...
</div>

<div class="message user-message">
    User message content here...
</div>
```

### Modals
```html
<div class="modal-overlay" id="modalId">
    <div class="modal-content">
        <div class="modal-header">
            <div class="modal-title">Modal Title</div>
            <div class="modal-close">
                <i class="fas fa-times"></i>
            </div>
        </div>
        <!-- Modal content here -->
    </div>
</div>
```

## Screen Archetypes

### Home Screen
**Purpose**: Main dashboard showing key insights and recent analyses
**Key Components**:
- Status bar
- Header with greeting and notification icon
- Insights card with personalized analysis
- Upload section for new content
- Analysis cards showing recent interactions
- Bottom navigation bar

### Chat Screen
**Purpose**: Interactive AI chat interface for analyzing relationships
**Key Components**:
- Status bar
- Chat header with title and settings
- Partner selection carousel
- Chat message container with AI and user messages
- Message input field with send button
- Bottom navigation bar

### Insights Screen (User Story)
**Purpose**: Detailed analytics about user's relationships and communication patterns
**Key Components**:
- Status bar
- Header with screen title
- Filter/time period selector
- Visualization charts for communication trends
- Detailed insights cards grouped by categories
- Recommendation sections
- Bottom navigation bar

### Upload Screen (User Story)
**Purpose**: Interface for uploading and categorizing conversation data
**Key Components**:
- Status bar
- Header with screen title
- Upload method selection (images, audio, text)
- Contact association interface
- Progress indicator
- Success/confirmation message
- Bottom navigation bar

### Profile Screen (User Story)
**Purpose**: User profile management and app settings
**Key Components**:
- Status bar
- User profile header with avatar
- Account settings section
- Privacy settings section
- Notification preferences
- Help and support options
- Bottom navigation bar

## CSS Base Structure
For consistency, all screens should include these base styles:

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Inter', sans-serif;
}

body {
    background-color: #f8f9fa;
    color: #333;
    max-width: 430px;
    margin: 0 auto;
    position: relative;
    min-height: 100vh;
    overflow-x: hidden;
}

/* Navigation Bar */
.navigation {
    position: fixed;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    justify-content: space-around;
    background-color: white;
    padding: 15px 0;
    border-radius: 30px;
    max-width: 90%;
    width: 350px;
    margin: 0 auto;
    z-index: 100;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}
```
