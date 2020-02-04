# tailwind-project

Hello World!

Building a basic website using HTML and TailwindCSS

Getting Started

Terminal (Be sure to have terminal to include destination folder)
"npm init -y" - Creates package.json
"npm install tailwindcss" - Installs tailwindcss to project folder

Create a folder "src"

Create file "style.css" and paste

    "@tailwind base;

    @tailwind components;

    @tailwind utilities;"

//* Instructions on how to run build command to build out css to include in HTML *//

Create a folder "dist"

Create files "index.html" and "style.css"

Open package.json
Replace "test": "echo \"Error: no test specified\" && exit 1" with "build:css": "tailwind build src/style.css -o dist/style.css"
Terminal "npm run build:css"

//* This will importing tailwindcss' framework (from src/style.css) into your dist style.css file *//

HTML should be ready to go with link to dist/style.css

Other Extensions Used

Live Server

Tailwind CSS IntelliSense

Stylelint 0.51.0 (thibaudcolas)
-Added because VSCode would flag tailwindcss rules as "unknown" and would generate multiple errors
-From https://stackoverflow.com/questions/47607602/how-to-add-a-tailwind-css-rule-to-css-checker
    1. Install Stylelint
    2. Install stylelint recommended config npm install stylelint-config-recommended --save-dev
    3. Add these two lines in your vscode USER SETTINGS

        "css.validate": false, //* Disable css built-in lint *//
        "stylelint.enable": true, //* Enable sytlelint *//
    4. Paste these lines into a file called .stylelintrc in your project's root directory, create it if it does not exist. More information about stylelint's configuration follow this link: https://stylelint.io/user-guide/

        {
        "extends": "stylelint-config-recommended",
        "rules": {
            "at-rule-no-unknown": [ true, {
            "ignoreAtRules": [
                "extends",
                "tailwind"
            ]
            }],
            "block-no-empty": null,
            "unit-whitelist": ["em", "rem", "s"]
        }
        }