# Neumorphic Calculator — JavaScript Calculator App

A modern, dark-themed **calculator web app** with a soft **neumorphic UI design**, built using pure **HTML5, CSS3, and vanilla JavaScript**. Supports basic arithmetic operations (addition, subtraction, multiplication, division, percentage) with a responsive, glowing button layout — no frameworks, no external libraries.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-success)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📸 Screenshot

![Calculator Screenshot](https://github.com/user-attachments/assets/dd9d0ec3-130b-413a-8387-2810565280cd)

## 🔍 About This Project

This **JavaScript calculator app** demonstrates how to build a fully functional calculator UI using core DOM APIs — `querySelectorAll`, dynamic event listeners, and string-based expression evaluation. Styled with a **neumorphic design** (soft shadows, dark background, glowing buttons), it's a great reference for developers searching for a **calculator app tutorial**, **JS calculator project**, or **neumorphism CSS example**.

## ✨ Features

- ➕ Basic arithmetic: addition, subtraction, multiplication, division, percentage
- 🔢 Numeric keypad including decimal point and "00" shortcut
- 🧹 Clear (`AC`) and single-character delete (`DEL`) functionality
- 🟢 Color-coded operator buttons (green) and equals button (orange) for visual clarity
- 🎨 Neumorphic (soft-UI) button and card styling with glow shadows
- ⚡ Zero dependencies — pure HTML/CSS/JS, no build step

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (Flexbox, neumorphic shadows, `linear-gradient`) |
| Logic | Vanilla JavaScript (DOM events, string evaluation) |
| Fonts | Google Fonts — Poppins |
| Dependencies | None |

## 📁 Project Structure

```
calculator-day5/
├── index.html      # Calculator markup — input display + button grid
├── style.css       # Neumorphic styling, layout, color coding
└── script.js       # Event handling and expression evaluation logic
```

## 🔍 How It Works

### `index.html`
A `.calculator` container holds a read-only-style `<input>` display and five rows of `<button>` elements — digits, operators (`class="operator"`), utility keys (`AC`, `DEL`, `%`), and an equals button (`class="equalBtn"`).

### `script.js`

```javascript
let input = document.getElementById("inputBox");
let buttons = document.querySelectorAll("button");

let string = "";
let arr = Array.from(buttons);

arr.forEach((button) => {
  button.addEventListener("click", (e) => {
    if (e.target.innerHTML == "=") {
      string = eval(string);
      input.value = string;
    } else if (e.target.innerHTML == "AC") {
      string = "";
      input.value = string;
    } else if (e.target.innerHTML == "DEL") {
      string = string.substring(0, string.length - 1);
      input.value = string;
    } else {
      string += e.target.innerHTML;
      input.value = string;
    }
  });
});
```

- All buttons are selected at once with `querySelectorAll("button")` and converted to an array so `.forEach` can attach a shared click handler to each
- A single `string` variable accumulates the expression as buttons are clicked, mirroring it into the input field on every keystroke
- `=` triggers `eval(string)`, which parses and computes the accumulated expression string as JavaScript
- `AC` resets the expression to an empty string
- `DEL` removes the last character using `substring(0, length - 1)`
- Every other button (digits, operators, `.`, `%`) simply appends its label to the expression string

### `style.css`
- Dark diagonal `linear-gradient` background (`#0a0a0a` → `#3a4452`)
- `.calculator` uses a translucent white background with a soft outer `box-shadow` for a floating glass-panel effect
- Buttons are circular (`border-radius: 50px`) with an inset-style glow shadow (`-8px -8px 15px rgba(255,255,255,0.1)`) — the core neumorphic technique
- `.operator` buttons are colored green (`#6dee0a`) and `.equalBtn` is solid orange (`#fb7c14`) to visually separate action keys from digits

## 🚀 Getting Started

No package manager, no build step — just open the file.

```bash
git clone https://github.com/your-username/calculator-day5.git
cd calculator-day5
```

Then open `index.html` directly in your browser.

## 🎯 What This Project Practices

- `querySelectorAll()` and looping over NodeLists via `Array.from()`
- Attaching shared event listeners across multiple elements
- String concatenation to build and evaluate an expression
- Basic use of `eval()` for expression parsing
- Neumorphic (soft-UI) CSS shadow techniques

## ⚠️ Known Limitations

- Uses `eval()` to compute results — fine for a learning project, but `eval()` should be avoided in production apps due to security risks (arbitrary code execution). A safer approach would use a proper expression parser or `Function()` constructor with input sanitization.
- No handling for malformed expressions (e.g. `5++`) — invalid input will throw an error via `eval()` rather than showing a friendly "Error" message.
- No keyboard input support — only clickable buttons currently work.

## 🧠 Possible Improvements

- Replace `eval()` with a safe custom expression parser
- Add keyboard support (`keydown` listener mapped to digits/operators)
- Add error handling that displays "Error" instead of throwing on invalid expressions
- Add a calculation history panel
- Add light/dark theme toggle

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](../../issues) or submit a pull request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## ⭐ Show Your Support

If this project helped you learn something, give this repo a ⭐ — it helps more developers discover it!

---

**Keywords:** javascript calculator app, neumorphic calculator ui, css neumorphism example, html css js calculator, vanilla javascript calculator tutorial, dom manipulation calculator project

**Topics:** `javascript` `html5` `css3` `calculator` `calculator-app` `vanilla-javascript` `neumorphism` `frontend` `dom-manipulation` `beginner-project` `web-development`
