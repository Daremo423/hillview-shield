# Codebase Summary: Hillview Resident Shield

## Project Overview
"Hillview Resident Shield" is a web-based application designed to assist residents of 1000 Hillview in documenting cockroach infestations and generating formal legal notices for their property management. It aims to provide safe reporting and legal protections.

## Tech Stack
The application is built using a simple, zero-build configuration:
- **HTML5**: The core structure is contained in a single `index.html` file.
- **React 18**: Loaded via CDN (unpkg) for UI rendering and state management.
- **Tailwind CSS**: Loaded via CDN for styling.
- **Lucide Icons**: Loaded via CDN for iconography.
- **Babel (Standalone)**: Loaded via CDN to compile JSX in the browser.

## Architecture
- **Single Page Application (SPA)**: The entire app resides within `index.html`.
- **No Build Process**: There are no `package.json`, build scripts, or local dependencies. The app runs directly in the browser by opening the HTML file.

## Key Features
1.  **Welcome Screen**:
    - Introduction to the app's purpose.
    - "Discreet Mode" toggle to disguise the app header.
    - Sharing functionality using a QR code generated via `api.qrserver.com`.
2.  **User Details**:
    - Input for Unit Number (required) and Name (optional).
3.  **Evidence Logging**:
    - Allows users to enter a date and description of the infestation.
    - Maintains a local list of logs (in-memory state).
4.  **Notice Generation (The Shield)**:
    - Generates a formal legal letter citing California Civil Code § 1941.1 and § 1942.5.
    - Allows users to download the letter as a `.txt` file.
5.  **Escalation**:
    - Provides external links to Milpitas City Inspectors and a Legal Hotline.
    - Option to erase session data.

## State Management
The application uses React's `useState` hook to manage:
- `currentStep`: Controls the navigation flow (welcome -> basics -> log -> shield -> escalate).
- `residentData`: Stores user inputs (name, unit number, sighting date, description).
- `logs`: An array of evidence logs.
- `isDiscreet`: Toggles the discreet mode UI.
- `showShare`: Toggles the sharing modal.
