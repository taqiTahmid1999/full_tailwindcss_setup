1. ```
   npm init
   ```
2. ```
   npm install tailwindcss @tailwindcss/postcss postcss
   ```
3. ```
   npm i -D cssnano prettier prettier-plugin-tailwindcss
   ```
4. ```
   npm i -g postcss-cli
   ``` \(if not installed)
5. ```
    mkdir assets main
   ```
6. ```
    touch assets/tailwind.css main/index.html main/styles.css .gitignore .prettierignore .prettierrc postcss.config.mjs
    ```
7. //assets/tailwind.css\
   ```
   @import "tailwindcss";
   ```
8. //main/index.html
```
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"
    />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Tailwind CSS</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <p class="h-12 w-24 bg-amber-300 text-center">Hello World</p>
  </body>
</html>  
```
9. make main/styles.css file type plain.txt
10. //.gitignore
``node_modules``
11. //.prettierignore
```
    node_modules
    main/styles.css
```
12. //.prettierrc
```
    {
      "plugins": ["prettier-plugin-tailwindcss"]
    }
```
13.//package.json
```
    {
  ...
  "scripts": {
    "build:css": "npx postcss assets/tailwind.css -o main/styles.css",
    "watch:css": "npx postcss assets/tailwind.css -o main/styles.css --watch"
  },
  ...
  "dependencies": {
    "@tailwindcss/postcss": "^4.0.9",
    "postcss": "^8.5.3",
    "tailwindcss": "^4.0.9"
  },
  "devDependencies": {
    "cssnano": "^7.0.6",
    "prettier": "^3.5.3",
    "prettier-plugin-tailwindcss": "^0.6.11"
  }
}
```
14. //postcss.config.mjs
```
export default {
  plugins: {
    "@tailwindcss/postcss": {},
    "cssnano": {
      preset: "default"
    }
  }
}
```
