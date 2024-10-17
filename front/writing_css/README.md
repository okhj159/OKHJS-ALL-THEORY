# Writing CSS

## 목차
1. [개요](#개요)
2. [Tailwind](#Tailwind)

## 개요
- 

## Tailwind
- GETTING STARTED
    - Installation
        - Installing Tailwind CSS as PostCSS plugin
            - Install Tailwind via npm
                - `npm install -D tailwindcss@latest postcss@latest autoprefixer@latest`
            - Add Tailwind as a PostCSS plugin
                - ```
                  // postcss.config.js
                  module.exports = {
                     plugins: {
                        tailwindcss: {},
                        autoprefixer: {},
                     }
                  }
                  ```
            - Create your configuration file
                - `npx tailwindcss init`
                - ```
                  // tailwind.config.js
                  module.exports = {
                     purge: [],
                     darkMode: false, // or 'media' or 'class'
                     theme: {
                        extend: {},
                     },
                     variants: {},
                     plugins: [],
                  }
                  ```
            - Include Tailwind in your CSS
                - ```
                  /* ./your-css-folder/styles.css */
                  @tailwind base;
                  @tailwind components;
                  @tailwind utilities;
                  ```
            - Building your CSS
                - ```
                    // tailwind.config.js
                    module.exports = {
                       purge: [
                          './src/**/*.html',
                          './src/**/*.js',
                       ],
                       darkMode: false, // or 'media' or 'class'
                       theme: {
                          extend: {},
                       },
                       variants: {},
                       plugins: [],
                    }
                  ```
- CORE CONCEPTS
    - Utility-First Fundamentals
        - Tailwind를 사용하면 기존 class를 HTML에 직접 적용하여 요소의 스타일을 지정할 수 있다.
    - Hover, Focus, and Other States
    - Responsive Design
    - Dark Mode
    - Reusing Styles
    - Adding Custom Styles
    - Functions & Directives
- CUSTOMIZATION
- BASE STYLES
- LAYOUT
- FLEXBOX AND GRID

<hr />