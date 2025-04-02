# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨
// Function to store user preferences in localStorage
function storePreference(key, value) {
    localStorage.setItem(key, value);
}

// Function to retrieve user preferences from localStorage
function getPreference(key) {
    return localStorage.getItem(key);
}

// Function to toggle animation on the box
function toggleAnimation() {
    const box = document.getElementById("animatedBox");
    box.classList.toggle("animating");

    // Store the animation state in localStorage
    const isAnimating = box.classList.contains("animating") ? "true" : "false";
    storePreference("isAnimating", isAnimating);
}

// Initialize the box state based on stored preferences
function initializeAnimation() {
    const isAnimating = getPreference("isAnimating");
    if (isAnimating === "true") {
        document.getElementById("animatedBox").classList.add("animating");
    }
}

// Event listener for the button click
document.getElementById("animateButton").addEventListener("click", toggleAnimation);

// Initialize animation state on page load
initializeAnimation();
