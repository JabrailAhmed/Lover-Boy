# LoverBoy aka Lover Boy Letters — Virtual Postcard Creator
Create a beautiful, modern virtual postcard. Choose your aesthetic, pen your message, and share it instantly.
A modern, highly aesthetic, minimalist web application built with **C#** and **ASP.NET Core Blazor** that allows users to design, customize, and share virtual postcards. Inspired by premium card creation platforms, this application features a real-time side-by-side editing canvas and responsive, modern component controls.

## ✨ Features

- 🎨 **Aesthetic Theme Palettes:** Instantly switch card backgrounds between premium texturized minimalist themes (Warm Linen, Warm Sunset, Forest Mist).
- ✍️ **Fluid Typography Options:** Real-time font pairing customization (Handwritten, Elegant, Modern) with live font-scaling support.
- 📐 **Golden Ratio Layout:** The postcard canvas utilizes a strict `1.618:1` aspect ratio to mirror real physical mail proportions.
- 📨 **Responsive Two-Column Editor:** Intuitively organizes text configurations side-by-side (Stacked input fields on the left, full message area on the right).
- 🖼️ **Custom Postmarks:** Supports on-the-fly image adjustments, converting uploaded files into base64 thumbnails to serve as decorative stamps.
- 🔗 **Secure Dynamic Routing:** Compiles all selected states dynamically into secure URL parameters for easy copy-and-paste sharing.

---

## 🛠️ Tech Stack & Tools
Framework: ASP.NET Core Blazor (InteractiveServer Render Mode)
Language: C# (.NET 9.0 preferred)
Styling: Tailwind CSS + Custom Decoupled Scoped Utility Layers

## 📁 Architecture & File Breakdown

The application follows a clean, decoupled design structure:

### 1. `Components/Pages/Create.razor`
Acts as the application storefront and workspace controller (`@page "/"`). It houses the primary HTML layout framework and the active C# state logic, handling asynchronous image parsing and query generation.

### 2. `wwwroot/app.css`
Contains the decoupled layout aesthetics wrapped inside Tailwind's `@layer utilities` declaration block. This prevents framework rule conflicts and ensures that critical card rendering details (like backdrop gradients and typography rules) operate cleanly with `!important` prioritizations.

### 3. `Components/App.razor`
The root application configuration engine. Imports custom font assets (like Google Fonts' *Caveat*, *Inter*, and *Playfair Display*) and forces hard browser cache-busting utilizing standard query version strings (`href="app.css?v=1.0.1"`).

---

## 🚀 Running the Project locally

1. Open JetBrains Rider on your Mac.
2. Choose Open Solution and select the `.sln` file.
3. Verify that the project target runtime matches `.NET 9.0`.
4. Press `Control + R` or click the Run button on the top toolbar.
5. Open your local browser to the provided port (e.g., `http://localhost:5000`).

Tip: When updating structural layout styles, use Rider's Hot Reload tool (`Cmd + Alt + R`) to seamlessly view design updates without resetting your compilation pipelines.

---

## 🔮 Future Roadmap Items
- [ ] Clean UI to make the process seamless and the view nicer of the eyes.
- [ ] Implement the Recipient View Page (`/view`) to parse data parameters and display static versions to recipients.
- [ ] Add an interactive 3D Card Flip Animation to let recipients flip between the postcard front and back surfaces.
- [ ] Connect a local SQLite database context to store postcards securely, moving away from query-string-heavy URLs.
