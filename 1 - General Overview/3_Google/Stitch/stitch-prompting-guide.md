# Stitch Prompting Guide: Designing Apps with AI

**Source**: Google Stitch - Docs (Learn: Prompting)  
**Purpose**: Comprehensive guide for crafting effective prompts to design and refine applications with Stitch AI

---

## Table of Contents
1. [Core Principles](#core-principles)
2. [Starting Your Project](#starting-your-project)
3. [Setting App Vibe & Style](#setting-app-vibe--style)
4. [Iterative Refinement Workflow](#iterative-refinement-workflow)
5. [Controlling App Theme](#controlling-app-theme)
6. [Modifying Images](#modifying-images)
7. [Changing App Language](#changing-app-language)
8. [Pro Tips & Best Practices](#pro-tips--best-practices)
9. [Real-World Use Cases](#real-world-use-cases)

---

## Core Principles

Stitch works best with **clear, specific, incremental instructions**. The key to effective prompting is:

- **Specificity**: Target exact elements and describe desired changes precisely
- **Focus**: Make one or two adjustments per prompt
- **Clarity**: Avoid ambiguity in language and instructions
- **Iteration**: Refine designs progressively through multiple prompts

---

## Starting Your Project

### High-Level vs. Detailed Prompts

**Choose your starting approach based on complexity:**

#### High-Level Approach
Start with a broad concept when you have a clear vision but flexible implementation details.

```
EXAMPLE: "An app for marathon runners."
```

**Best for**: Simple apps with clear primary purpose; rapid prototyping phase

#### Detailed Approach
Include core functionalities upfront for a stronger starting point with complex features.

```
EXAMPLE: "An app for marathon runners to engage with a community, 
find training partners, get real-time coaching advice, and discover races 
near their location."
```

**Best for**: Multi-feature applications; apps requiring specific functionality hierarchy

---

## Setting App Vibe & Style

### Using Adjectives to Define Feel

Adjectives directly influence design decisions—colors, typography, imagery, and overall aesthetic. Choose 1-3 adjectives that clearly convey your desired mood.

#### Examples of Effective Adjectives

**Fitness-Focused Apps:**
```
"A vibrant and encouraging fitness tracking app."
```
→ Expects: Bright colors, energetic typography, motivational imagery

**Wellness & Mindfulness:**
```
"A minimalist and focused app for meditation."
```
→ Expects: Neutral palette, clean whitespace, serene imagery

**Professional Tools:**
```
"A modern and trustworthy project management dashboard."
```
→ Expects: Professional typography, subtle colors, organized layouts

**Creative Platforms:**
```
"A bold and playful music creation app."
```
→ Expects: Vibrant colors, expressive typography, dynamic imagery

**Note**: Adjectives shape the entire visual direction—be intentional about tone.

---

## Iterative Refinement Workflow

### The Incremental Change Strategy

Stitch performs optimally when you refine **one screen/component at a time** with **1-2 specific changes per prompt**.

### Anatomy of an Effective Refinement Prompt

A strong refinement prompt contains:

1. **Target Specification** (what you're changing)
2. **Current/Specific Element** (which exact component)
3. **Desired Change** (how it should change)
4. **Context/Style Reference** (optional: brand reference, visual style)

#### Formula:
```
[Element Location] + [Specific Element] → [Desired Change] + [Brand/Style Context]
```

### Strong Refinement Examples

#### Example 1: Login Screen CTA Button
```
PROMPT: "Change the primary call-to-action button on the login screen to be 
larger and use the brand's primary blue color (#0066CC)."
```

**Components Present**:
- ✓ Target screen: "login screen"
- ✓ Specific element: "primary call-to-action button"
- ✓ Changes: "larger" + "primary blue color"
- ✓ Precise color reference: hex code

#### Example 2: E-Commerce Product Detail (Japandi Tea Store)
```
PROMPT: "Product detail page for a Japandi-styled tea store selling herbal teas 
and ceramics. Use neutral, minimal colors, black buttons, and soft, elegant serif font. 
Layout should emphasize white space between product images and descriptions."
```

**Components Present**:
- ✓ Screen type: "Product detail page"
- ✓ Brand style: "Japandi-styled" (specific aesthetic)
- ✓ Product context: "herbal teas, ceramics" (informs imagery)
- ✓ Color direction: "neutral, minimal"
- ✓ Button style: "black buttons"
- ✓ Typography: "soft, elegant serif font"
- ✓ Layout principle: "white space emphasis"

#### Example 3: E-Commerce Product Detail (Workwear Apparel)
```
PROMPT: "Product detail page for Japanese workwear-inspired men's athletic apparel. 
Use a dark, minimal design with dark blue (#1a3a52) as primary color. Minimize clothing 
pictures (show only 2-3 high-quality shots), emphasize natural fabric photography, 
and avoid gaudy visual elements."
```

**Components Present**:
- ✓ Screen type: "Product detail page"
- ✓ Brand inspiration: "Japanese workwear-inspired"
- ✓ Design principle: "dark, minimal"
- ✓ Specific color: "dark blue with hex code"
- ✓ Image strategy: "minimize pictures, show only 2-3"
- ✓ Visual guidance: "natural fabrics, not gaudy"

---

## Controlling App Theme

### Colors

#### Specific Color Requests
Use exact color names or hex codes for precision:

```
PROMPT: "Change primary color to forest green."
PROMPT: "Update primary accent to #2D5016 and secondary to #F5E6D3."
```

#### Mood-Based Color Requests
Describe the emotional tone to let Stitch interpret the palette:

```
PROMPT: "Update theme to a warm, inviting color palette that feels welcoming and cozy."
PROMPT: "Shift to a cool, professional palette with blues and grays."
```

**When to use each approach:**
- **Specific colors**: Brand guidelines exist; precise control needed
- **Mood-based**: Exploring direction; want AI interpretation; brand flexibility

---

### Fonts & Borders

#### Typography
Modify headline and body typography separately for fine-grained control:

```
PROMPT: "Use a playful sans-serif font for all UI text."
PROMPT: "Change headings to a serif font; keep body text in clean sans-serif."
PROMPT: "Use a modern geometric sans-serif (like Inter or Poppins) for headers."
```

#### Borders & Button Styling
Define button shapes, input field styling, and container borders:

```
PROMPT: "Make all buttons have fully rounded corners (border-radius: 50%)."
PROMPT: "Give input fields a 2px solid black border with rounded corners."
PROMPT: "Update card containers to have subtle shadows and 12px rounded corners."
```

#### Combined Theme Example
```
PROMPT: "Book discovery app: use serif font (like Garamond) for text, 
light green (#A8D5BA) as brand color for accents and CTA buttons, 
and minimalist card layouts with subtle shadows."
```

---

## Modifying Images

### Be Specific When Targeting Images

Images are powerful design elements. Identify them clearly:

#### Targeting General Images (Multiple Instances)
```
PROMPT: "Change background of all product images on the landing page to light taupe."
```

**Structure**: `[Scope: all/specific] [image type] on [screen/section]` → `[change description]`

#### Targeting Specific Images (Single Instance)
```
PROMPT: "On the 'Team' page, update the image of 'Dr. Carter (Lead Dentist)' 
to show her wearing a black lab coat instead of white."
```

**Structure**: `On [screen], image of [identifier]` → `[specific change]`

### Coordinating Images with Theme Changes

When updating color themes, specify image adjustments:

```
PROMPT: "Update theme to light orange (#F4A460). Ensure all images and 
illustrative icons match this new color scheme—adjust overlays, filters, 
and icon colors accordingly."
```

**Key consideration**: Images may need color adjustments, filter overlays, or illustrative element updates to align with new theme.

---

## Changing App Language

Use a simple, direct prompt to switch all text content:

```
PROMPT: "Switch all product copy and button text to Spanish."
PROMPT: "Translate entire app interface to French, keeping brand name unchanged."
PROMPT: "Change all user-facing text to German; maintain technical field labels as-is."
```

---

## Pro Tips & Best Practices

### ✓ Clarity & Precision
- **Avoid ambiguity**: Instead of "make it better," say "increase button size by 20%"
- **Use exact terminology**: "call-to-action button" vs. "the button thing"
- **Specify locations**: "on the login screen" vs. "somewhere on the app"

### ✓ Iteration & Experimentation
- **Refine progressively**: Make small changes, review, then adjust
- **Test multiple directions**: Try different color palettes or font combinations
- **Build incrementally**: Start simple, add complexity screen by screen

### ✓ One Major Change at a Time
- **Easier to evaluate**: You'll clearly see what worked
- **Faster iteration**: If something doesn't work, you know what caused it
- **Better refinement**: Subtle adjustments compound into polished designs

### ✓ Use UI/UX Keywords
Stitch understands standard design terminology:
- Navigation structures: "navigation bar," "hamburger menu," "tab navigation"
- Components: "card layout," "modal dialog," "toast notification"
- Buttons: "primary button," "secondary button," "call-to-action button"
- Sections: "hero section," "footer," "sidebar"

### ✓ Reference Elements Specifically
Instead of: "Change the button"  
Say: "Change the primary button on the sign-up form"

Instead of: "Update the image"  
Say: "Update the hero section image on the landing page"

### ✓ Review & Refine
If results aren't as expected:
- **Rephrase**: Try different wording or terminology
- **Be more targeted**: Narrow the scope further
- **Provide examples**: Reference similar designs or styles
- **Ask for alternatives**: Request multiple directions to explore

---

## Real-World Use Cases

### Use Case 1: SaaS Dashboard for Fitness Trainers

**Project Brief**: Build a trainer management app for personal fitness coaches to schedule clients, track progress, and manage billing.

#### Phase 1: High-Level Concept
```
PROMPT: "Create a fitness trainer management app. Core features: client 
scheduling, progress tracking, workout library, and billing dashboard."
```

#### Phase 2: Set Overall Vibe
```
PROMPT: "Design with a professional yet approachable feel—modern, energetic, 
and trustworthy. Use an active blue as primary color."
```

#### Phase 3: Refine Screens Incrementally

**Dashboard Screen**:
```
PROMPT: "Design the main dashboard to show 'Today's Clients' at top, upcoming 
sessions in a card grid below, and quick stats (revenue, active clients) in the 
footer. Use minimal design with lots of white space."
```

**Client Detail Screen**:
```
PROMPT: "Build a client detail page with profile photo on left, stats (weight, 
measurements, goal) in the center, and workout history on right. Use a clean, 
minimal layout with serif font for headers."
```

**Billing Screen**:
```
PROMPT: "Create a billing dashboard showing monthly revenue chart, upcoming 
invoices, and payment methods. Use professional styling with dark blue primary 
color (#1a3a52), subtle borders on all cards, and sans-serif font."
```

#### Phase 4: Theme & Polish
```
PROMPT: "Update all brand colors: primary to active blue (#0066CC), secondary 
to light gray (#F0F0F0). Make all buttons fully rounded (border-radius: 50%) 
and use a modern sans-serif font (Inter or similar)."
```

**Outcome**: A polished, professional trainer dashboard with clear hierarchy, intuitive navigation, and cohesive design system.

---

### Use Case 2: E-Commerce Marketplace for Artisan Ceramics

**Project Brief**: Build an online marketplace for independent ceramic artists to showcase and sell handmade pieces.

#### Phase 1: Initial Direction
```
PROMPT: "Create an artisan ceramic marketplace where independent potters can 
sell handmade bowls, vases, mugs, and decorative pieces. Include product browsing, 
artist profiles, and reviews."
```

#### Phase 2: Establish Aesthetic
```
PROMPT: "Design with a warm, earthy, and artisanal feel. Use natural, neutral 
colors (creams, warm browns, soft whites). Emphasize beautiful product photography 
and artist craftsmanship."
```

#### Phase 3: Product Detail Page Refinement
```
PROMPT: "Product detail page: large, centered hero image (let product breathe), 
artist name and bio on right side, description in warm serif font, and 'Add to Cart' 
button in warm terracotta color (#A0522D). Include high-res close-up images below."
```

#### Phase 4: Artist Profile Refinement
```
PROMPT: "Artist profile: feature artist photo at top with bio, followed by a 
grid of their work (3-4 pieces per row), reviews below. Use a soft cream background 
(#F5F1E8) with minimal borders. Emphasize the human connection and craftsmanship."
```

#### Phase 5: Image & Theme Coordination
```
PROMPT: "Update theme: primary color to warm terracotta (#A0522D), accent color 
to sage green (#9CAF88). Adjust all product images to have a warm, natural lighting 
filter. Ensure artist photos feel authentic and organic."
```

**Outcome**: A beautiful, artisan-focused marketplace that celebrates craftsmanship and builds trust through authentic imagery and warm design.

---

### Use Case 3: Community Health Platform for Underserved Neighborhoods

**Project Brief**: Build a platform connecting low-income residents with free/low-cost health resources, clinics, mental health support, and wellness events.

#### Phase 1: Core Concept
```
PROMPT: "Create a community health resource app for underserved neighborhoods. 
Features: find nearby clinics, book appointments, access mental health resources, 
find wellness events, and share community knowledge."
```

#### Phase 2: Tone & Accessibility
```
PROMPT: "Design with a welcoming, accessible, and empowering feel. Use bright, 
encouraging colors and clear, readable fonts. Make it accessible to all age groups 
and literacy levels. Avoid clinical or institutional styling."
```

#### Phase 3: Home Screen Refinement
```
PROMPT: "Home screen: prominent search bar at top for finding clinics, 3-4 large 
cards below for main categories (Clinics, Mental Health, Wellness, Events). Use 
simple icons and clear language. Include a 'Resources Near You' section with map view."
```

#### Phase 4: Clinic Finder Refinement
```
PROMPT: "Clinic finder page: map at top with clinic markers, list view below 
showing clinic name, distance, services offered, and hours. Include filtering by 
service type and language spoken. Use icons for clarity."
```

#### Phase 5: Mental Health Resource Refinement
```
PROMPT: "Mental health resources page: prominent crisis hotline number at top 
(large, easy to tap). Below: categories (Therapy, Support Groups, Self-Help, Crisis), 
each with filterable resources. Include brief descriptions and access instructions."
```

#### Phase 6: Theme & Polish
```
PROMPT: "Update theme: primary color to warm, encouraging teal (#4A9B7D), secondary 
to warm orange (#E8804C) for CTAs. Use a friendly, readable sans-serif font (like 
Open Sans). Ensure all buttons are large and easy to tap. Add illustrations of 
diverse people using the app."
```

**Outcome**: An accessible, welcoming health platform that removes barriers to care and empowers community members to find resources.

---

### Use Case 4: Indie Game Studio Portfolio & Game Launcher

**Project Brief**: Build a portfolio website + game launcher for a small indie game studio with 5-6 games across different genres.

#### Phase 1: Initial Vision
```
PROMPT: "Create a portfolio and game launcher for an indie game studio. Show 
game libraries, individual game pages, developer bios, and press kit. Include 
download/play functionality."
```

#### Phase 2: Brand Personality
```
PROMPT: "Design with a bold, creative, and playful aesthetic that reflects indie 
game culture. Use vibrant colors, modern typography, and dynamic layouts. Emphasize 
creativity and personality over corporate polish."
```

#### Phase 3: Game Browse Page
```
PROMPT: "Game library page: show 2-3 game cards per row, each with large cover art, 
title, genre, and brief description. Use a dark background (#1a1a1a) to make artwork 
pop. Cards should have hover effects (slight lift). Include filter by genre (Action, 
Puzzle, Story-Driven, etc.)."
```

#### Phase 4: Individual Game Page
```
PROMPT: "Game detail page: hero image at top (full-width), title and description 
below, key features in bulleted list, 4-6 screenshot gallery, reviews/ratings, 
and large 'Download' or 'Play Now' button. Use vibrant accent color for CTA."
```

#### Phase 5: Image & Visual Strategy
```
PROMPT: "All game cover art and screenshots should feature vibrant, saturated colors. 
Update theme: primary to electric purple (#6A0572), secondary to neon cyan (#00D9FF). 
Use bold sans-serif font (like Syne or Bebas Neue) for headers. Add glow effects 
to CTAs."
```

#### Phase 6: Developer Profiles
```
PROMPT: "Developer bio pages: feature portrait photo (left), name and role (center), 
bio and socials (right). Use the vibrant neon accent colors. Add a 'See Their Games' 
section below linking to relevant titles."
```

**Outcome**: A bold, engaging studio portfolio that attracts indie game enthusiasts and clearly showcases each game's personality.

---

### Use Case 5: Nonprofit Volunteer Coordination Platform

**Project Brief**: Build a platform for nonprofits to recruit, schedule, and manage volunteers for events, ongoing programs, and one-off tasks.

#### Phase 1: Core Concept
```
PROMPT: "Create a volunteer coordination platform for nonprofits. Features: 
volunteer signup, opportunity browsing, event calendar, hours tracking, and 
impact dashboard showing volunteer contributions."
```

#### Phase 2: Mission-Driven Aesthetic
```
PROMPT: "Design with warmth, trust, and community spirit. Use colors that feel 
inclusive and hopeful (soft greens, warm oranges). Typography should feel 
accessible and human, not corporate. Emphasize community impact."
```

#### Phase 3: Opportunity Listing Page
```
PROMPT: "Volunteer opportunities page: show opportunities as cards in a 2-column grid. 
Each card displays: organization name, opportunity title, date/time, commitment level 
(one-time/ongoing), location, and 'Learn More' button. Include a search and filter 
(by date, location, cause)."
```

#### Phase 4: Opportunity Detail Page
```
PROMPT: "Opportunity detail: hero image (organization or cause-related), clear title 
and description, volunteer requirements, time commitment, location with map, and large 
'Sign Up' button. Include impact statement ('Your help will provide X meals' etc.)."
```

#### Phase 5: Volunteer Dashboard
```
PROMPT: "Volunteer dashboard: show upcoming shifts at top, 'Hours This Month' card, 
'Impact' card showing total hours and causes supported, and a 'Recommended for You' 
section. Use warm green (#7CB342) for accents and impact messaging."
```

#### Phase 6: Final Polish
```
PROMPT: "Update theme: primary color to warm green (#7CB342), secondary to warm 
orange (#FF9800) for engagement CTAs. Use a friendly, readable font (Poppins or 
Oxygen). Add illustrations of diverse volunteers and community members. Ensure all 
language is inclusive and impact-focused."
```

**Outcome**: A warm, mission-focused volunteer platform that builds community connection and clearly communicates the value of volunteering.

---

## Summary

**Stitch Prompting Success = Specificity + Iteration + Clear References**

1. **Start strong**: Choose high-level or detailed approach based on complexity
2. **Set tone**: Use 1-3 descriptive adjectives to guide aesthetic
3. **Refine methodically**: One screen, 1-2 changes per prompt
4. **Be precise**: Reference specific elements with UI/UX terminology
5. **Control theme**: Use colors, fonts, and borders consistently
6. **Guide imagery**: Describe image style and coordinate with theme
7. **Iterate**: Review, refine, and rephrase until results match vision

---

## Quick Reference: Prompt Formula

```
[Scope/Screen] + [Element] + [Change/Direction] + [Style Context]
```

**Example**: "On the login screen, make the primary CTA button larger and 
change it to brand blue (#0066CC) with fully rounded corners."
