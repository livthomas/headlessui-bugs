# Vue Scoped Styles Bug

This project contains a reproducer of a bug in Headless UI.
The `Dialog` and other components from this library cannot be properly styled when using scoped styles in Vue.

## Steps To Reproduce

1. Install all npm dependencies:

    ```
    npm install
    ```

2. Start the application:

    ```
    npm run dev
    ```

3. Open http://localhost:3000/ in your browser.
4. Click on buttons and see the difference between the two dialogs.
