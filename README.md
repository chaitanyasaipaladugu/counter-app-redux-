# Counter App (React + Redux Toolkit)

Simple counter application built with React and Redux Toolkit. It demonstrates a minimal state slice, a configured store, and a component using `useSelector` and `useDispatch` to read and update state.

### Features

- Increment, decrement, and reset the counter
- Centralized state management via Redux Toolkit slice
- `Provider`-wrapped app with a configured store
- Clean, beginner-friendly project structure

## Prerequisites

- Node.js 18+ and npm 8+

## Quick Start

1. Navigate to the app folder:

```bash
cd counter-app
```

2. Install dependencies:

```bash
npm install
# If Redux packages are missing (first-time setup), also run:
npm i @reduxjs/toolkit react-redux
```

3. Start the development server:

```bash
npm start
```

4. Open `http://localhost:3000` in your browser.

## Project Structure

```text
counter-app/
  public/
    index.html           # Root HTML with <div id="root"></div>
  src/
    App.js               # Renders the Counter component
    index.js             # React entry, wraps App with Redux Provider
    index.css            # Global styles (optional)
    components/
      Counter.js         # UI: buttons + current count
    redux/
      store.js           # Configures Redux store
      counterSlice.js    # Slice with increment/decrement/reset reducers
```

## How It Works

- `redux/counterSlice.js` defines the `counter` slice with `count` in state and three reducers.
- `redux/store.js` registers the slice reducer under `counter`.
- `index.js` creates a React root and renders `<App />` inside a Redux `Provider`.
- `components/Counter.js` uses `useSelector` to read `state.counter.count` and `useDispatch` to send `increment`, `decrement`, and `reset` actions.

## Available Scripts

- `npm start`: Run the app in development mode at `http://localhost:3000`.
- `npm run build`: Create a production build in the `build/` directory.
- `npm test`: Run tests in watch mode (if you add tests).

## Troubleshooting

- Blank screen or nothing renders:
  - Ensure `App.js` returns JSX: `return <Counter />;`
  - Make sure Redux deps are installed: `npm i @reduxjs/toolkit react-redux`
  - Check browser console for runtime errors and fix missing imports.
  - Confirm `public/index.html` contains `<div id="root"></div>`.
- Port already in use: stop other apps on port 3000 or run with a different port.

## License

MIT (for learning/demo purposes)
