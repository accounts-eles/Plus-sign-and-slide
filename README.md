🗂️ Slide-Up Reveal Grid

A sophisticated, interactive grid system built with Tailwind CSS. This component features "image-first" cards that slide up a high-contrast information panel when triggered by a floating action button. It is ideal for portfolios, team bios, or interactive product features.

🚀 Live Demo

Explore the Slide-Up Reveal Component Here

✨ Project Overview

The Slide-Up Reveal Grid focuses on visual storytelling. By keeping the interface clean and image-heavy initially, it encourages user engagement via the floating "plus" icons. When clicked, a smooth CSS-driven animation covers the image with detailed textual content.

Key Features

Sliding Panel Animation: Uses absolute positioning and bottom: -100% transitions combined with a cubic-bezier timing function for a professional, "app-like" sliding feel.

Floating Action Triggers: Each card features a high-contrast circular "plus" icon that acts as the primary toggle for the reveal state.

Auto-Close Logic: The JavaScript controller ensures that opening one panel automatically closes any others, maintaining a clean and focused user experience.

Responsive Masonry-Style Grid: A fluid layout that transitions from 1 column (mobile) to 2 columns (tablet) and 3 columns (desktop) using Tailwind’s native breakpoints.

Tap-to-Dismiss: Users can click the active panel or anywhere on the page body to dismiss the revealed information, adhering to modern mobile interaction patterns.

🛠️ Technical Implementation

Tailwind JIT Configuration: Utilizes an inline tailwind.config object to define a semantic color palette (brand-dark, brand-accent, etc.) and the Inter font family.

CSS State Management: Leverages an .active class on the parent .reveal-item to drive both the panel movement and icon visibility.

Optimized Images: Includes object-cover styling and a JavaScript onerror fallback to ensure the UI remains intact even if external assets fail to load.

Visual Design Tokens:

Brand Dark (#1f2a52): Primary text color and subtle drop shadows.

Brand Accent (#00bec7): Reveal panel background and icon color.

Brand Light (#d2f0f0): Overall page background and icon container.

📂 Structure and Usage

The component is self-contained and utilizes a specialized event delegation pattern to handle interactions efficiently.

Reveal Item: The root container with overflow: hidden to mask the off-screen panel.

Plus Icon: The trigger element positioned in the bottom-right corner.

Info Panel: The hidden content layer that slides into view.

// Interaction Controller Logic
const closeAllPanels = (currentItem) => {
    revealItems.forEach(item => {
        if (item !== currentItem && item.classList.contains('active')) {
            item.classList.remove('active');
        }
    });
};

plusIcon.addEventListener('click', (event) => {
    event.stopPropagation();
    closeAllPanels(item);
    item.classList.toggle('active');
});


📄 License

MIT License - Developed as part of the accounts-eles UI component library.
