# Gelonezi ExplorerIO Frontend

[![GitHub Repo](https://img.shields.io/badge/github-gelonezi%2Fexplorerio--frontend-blue)](https://github.com/gelonezi/explorerio-frontend)
[![Angular CLI](https://img.shields.io/badge/angular–cli-v16.2.0-red.svg)](https://cli.angular.io/)

The **Gelonezi ExplorerIO Frontend** is an Angular application that provides a folder-style, Explorer-like UI for browsing and previewing files across multiple cloud storage backends (via the ExplorerIO API/SDK).

---

## Features (coming soon)

- 📂 **Folder Navigation** Browse S3 buckets (and future providers) in a tree-view directory structure.
- 📝 **Metadata Display** Show file details (size, last modified, custom metadata) in a side panel.
- 🔗 **Deep Linking** Bookmark or share direct links to any folder or file view.
- 💨 **Virtual Scrolling** Efficiently render large lists of files and folders.
- 🎨 **Responsive Design** Optimized for desktop and tablet layouts.

---

## Prerequisites

- [Node.js ≥18](https://nodejs.org/)
- [npm ≥9](https://www.npmjs.com/) or [Yarn](https://yarnpkg.com/)
- [Angular CLI ≥16](https://angular.io/cli)

---

## Installation

1. **Clone the repository**

    ```bash
    git clone https://github.com/gelonezi/explorerio-frontend.git
    cd explorerio-frontend
    ````

2. **Install dependencies**

    ```bash
    npm install
    # or
    yarn install
     ```

3. **Configure environment**
    Copy `src/environments/environment.example.ts` to `environment.ts` and update the API URL and default credential key:

    ```ts
    export const environment = {
    production: false,
    apiBaseUrl: 'https://localhost:5001/api/v1',
    defaultCredentialKey: 'default'
    };
    ```

---

## Development Setup

1. **Serve locally**

    ```bash
    ng serve
    ```

    Navigate to `http://localhost:4200/`.

2. **Run unit tests**

    ```bash
    ng test
    ```

3. **Build for production**

    ```bash
    ng build --configuration production
    ```

---

## Project Structure

```text
explorerio-frontend/
├── src/
│ ├── app/
│ │ ├── core/ # Services, models, and guards
│ │ ├── shared/ # Reusable components (tree-view, file-card)
│ │ ├── features/ # Feature modules (browser, preview, auth)
│ │ ├── environments/ # environment.ts / environment.prod.ts
│ │ └── app.module.ts
│ ├── assets/ # Static assets (icons, styles)
│ └── index.html
├── e2e/# End-to-end tests (Protractor/Cypress)
├── angular.json
├── package.json
└── README.md
```

---

## Usage Example

Within your Angular component or service, you can inject the ExplorerIO client service:

```ts
import { ExplorerService } from './core/services/explorer.service';

@Component({ … })
export class BrowserComponent implements OnInit {
constructor(private explorer: ExplorerService) {}

async ngOnInit() {
const folders = await this.explorer.listRootFolders();
this.rootFolders = folders;
}
}
```

---

## Documentation & Contributions

Full documentation at [exploreriodocs.gelonezi.com](https://exploreriodocs.gelonezi.com).

Guidelines for Contributions is available in the full documentation.

---

*This README will evolve alongside the frontend, adding more setup details, theming instructions, and component-level docs.*
