# ui-ux-first-project

This is my first project for learning how to build a simple website using HTML and CSS.

## Project Files

- `html/myfirst.html` — the HTML file that contains the page structure.
- `stylesheet/myfirst.css` — the CSS file that contains page styling.

## What this project shows

- A basic HTML document structure with `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.
- A linked CSS stylesheet using the `<link>` tag.
- Common HTML elements like headings (`<h1>`, `<h2>`), paragraphs (`<p>`), lists (`<ul>`, `<li>`), and links (`<a>`).
- Simple CSS styling for layout, colors, spacing, and hover effects.

## How to view the page

1. Open `html/myfirst.html` in a web browser.
2. The browser will load the page and apply styles from `stylesheet/myfirst.css`.
3. Make changes in the HTML or CSS files and refresh the browser to see updates.

## Changes in local Nginx tp serve the page in browser via http

### Server block to serve the project folder at http://localhost/ui-ux-first-project/
### Copy this server block into your main nginx.conf (inside the `http` context)
### or place this file in conf/ and add an `include` directive in nginx-rot-dir\conf\nginx.conf and re-start Nginx server

```bash
server {
    listen       80;
    server_name  localhost;

    # Set root to the workspace parent so requests map directly:
    root "C:/Users/Aditi Srivastava/Desktop/workspace/web-dev";
    index index.html myfirst.html;

    # Serve the project at path /ui-ux-first-project/
    location /ui-ux-first-project/ {
        # Files are served from: C:/Users/Aditi Srivastava/Desktop/workspace/web-dev/ui-ux-first-project/
        try_files $uri $uri/ =404;
        autoindex on;
    }

    # Default: return 404 for other requests
    location / {
        try_files $uri $uri/ =404;
    }
}
```

With the above change you csn open the file in your browser vi the http url --> http://localhost/ui-ux-first-project/html/myfirst.html

## Notes

- The CSS file is linked with a relative path: `../stylesheet/myfirst.css`.
- This project is a good starting point for practicing HTML structure and CSS styling.
- You can expand it by adding more sections, images, and layout styles.
