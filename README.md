# Simple Clicker

A minimalist web-based click counter that allows users to track the number of times they click a button. The application is built with HTML, CSS, and JavaScript, and is designed to render well on both desktop and mobile devices. The counter can be incremented by clicking the "Click Me!" button, and it can be reset using the "Reset" button.

## Features

- **Simple and Intuitive Interface**: The application consists of two buttons, one for incrementing the counter and one for resetting it to zero.
- **Responsive Design**: The page is fully responsive and adapts to different screen sizes, making it easy to use on both desktop and mobile devices.
- **Fast and Lightweight**: The app uses plain HTML, CSS, and JavaScript, without any external libraries or frameworks, ensuring fast performance.

<!-- ## Demo

You can see a live demo of the Simple Clicker [here](#). -->

## Code Overview

### HTML Structure

- The `div` with `id="countDisplay"` is used to display the current count.
- The `button` elements trigger JavaScript functions to either increment the counter or reset it.

### CSS Styling

- The page is styled using basic CSS, with a flexbox layout to center the content vertically and horizontally.
- Buttons are styled with distinct colors: green for incrementing and red for resetting, making them easy to differentiate.

### JavaScript Logic

- The counter is stored in the `count` variable and updated each time the user clicks the "Click Me!" button.
- The `incrementCounter()` function increments the counter and updates the display.
- The `resetCounter()` function resets the counter to zero.

## How to Use

1. Clone or download the repository.
2. Open the `index.html` file in any web browser.
3. Click the "Click Me!" button to increment the counter.
4. Use the "Reset" button to reset the count to zero.

## License

This project is licensed under the MIT License. Feel free to use, modify, and distribute this code as needed.

---

Happy clicking! 🚀
