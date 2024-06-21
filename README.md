# README

## About

Minimal Nuxt template for Wails. Leverage the developer experience of Nuxt with amazing speed of
Wails to create cross-platform GUI apps.

## Auto-import
👉 Supports runtime auto-import out of the box
🫸 Doesn't support bindings auto-import due to the possible function name collisions

## Installation
1. Install go and Wails https://wails.io/docs/gettingstarted/installation 
2. Create a project using
```
wails init -n "Your Project Name" -t https://github.com/gornius/wails-template-nuxt
```

## Live Development

To run in live development mode, run `wails dev` in the project directory. In another terminal, go into the `frontend`
directory and run `npm run dev`. The frontend dev server will run on http://localhost:34115. Connect to this in your
browser and connect to your application.

## Building

To build a redistributable, production mode package, use `wails build`.
