# Vue UI Extensions

> Upgrade-friendly customization for official Frappe Vue applications.

Vue UI Extensions is an open-source Frappe app that lets you customize official Vue-based applications—such as **HRMS** and **Helpdesk**—without modifying or forking the upstream projects.

Instead of maintaining a fork, simply override the Vue components you want, build once, and continue receiving upstream updates with a much simpler maintenance workflow.

---

## Why Vue UI Extensions?

Frappe has an excellent customization story for traditional Desk applications through:

- Client Scripts
- Server Scripts
- Hooks
- Custom Fields
- Custom Apps

However, many newer Frappe products are built as standalone Vue applications.

Examples include:

- HRMS
- Helpdesk
- CRM
- LMS
- Drive
- Gameplan

These applications cannot be customized using traditional Desk customizations.

Today, developers typically have three options:

- Fork the application and maintain it forever
- Modify upstream source files and lose changes during updates
- Rebuild the frontend from scratch

None of these approaches scale well.

Vue UI Extensions fills this gap by providing an upgrade-friendly customization layer for Vue applications.

---



## Features

- Override individual Vue components
- No upstream source modifications
- No long-lived forks
- Upgrade-friendly workflow
- Supports multiple Vue applications
- Easy to extend for new Frappe Vue apps
- MIT Licensed
- Open Source

---



## How It Works

Vue UI Extensions follows a simple convention.

Mirror the upstream Vue component structure inside your custom app:

```text
vue_ui_extensions/
└── extensions/
    └── hrms/
        └── overrides/
            └── components/
                └── CheckInPanel.vue
```

During the build process the application:

1. Copies the target application's frontend into a temporary workspace.
2. Applies your override files.
3. Builds the application using the original Vite configuration.
4. Serves the customized frontend while leaving the upstream project untouched.

Only your override files are maintained.

---



## Supported Applications

Current support:

- HRMS
- Helpdesk
- Additional Vue-based Frappe applications

---



## Why Not Fork?


| Approach              | Upgrade Friendly | Easy to Maintain |
| --------------------- | ---------------- | ---------------- |
| Fork the application  | ❌                | ❌                |
| Modify upstream files | ❌                | ❌                |
| Rewrite the frontend  | ❌                | ❌                |
| Vue UI Extensions     | ✅                | ✅                |


---



## Requirements

- Frappe v16+
- Python 3.14+
- Node.js 18+
- Yarn
- Target Vue application installed (HRMS, Helpdesk, etc.)

---



## Installation

```bash
bench get-app https://github.com/usman8786/Vue-UI-Extensions.git
bench --site <site> install-app vue_ui_extensions
```

Install Vue UI Extensions after installing the target applications.

---



## Override Convention

Mirror the upstream `src/` structure.

Example:

```text
extensions/helpdesk/overrides/components/layouts/Sidebar.vue
```

replaces

```text
helpdesk/desk/src/components/layouts/Sidebar.vue
```

Likewise,

```text
extensions/hrms/overrides/components/CheckInPanel.vue
```

replaces

```text
hrms/frontend/src/components/CheckInPanel.vue
```

---



## Build

```bash
bench build --app vue_ui_extensions
```

After building:

```bash
bench --site <site> clear-cache
```

Refresh your browser and your customized Vue application is ready.

---



## Upgrade Workflow

When a new version of HRMS or Helpdesk is released:

1. Update your applications.
2. Compare your overridden components with upstream changes.
3. Rebuild Vue UI Extensions.
4. Verify your customizations.

No fork maintenance.
No merge conflicts.
Only the components you customized.

---



## Roadmap

- Support additional official Vue applications
- Better developer tooling
- Improved build performance
- Documentation and examples
- Community-contributed extensions

---



## Contributing

Contributions are welcome.

Whether it's bug reports, feature requests, documentation improvements, or support for additional Vue applications, every contribution helps make frontend customization easier for the Frappe ecosystem.

---



## License

MIT License.

Free to use in personal and commercial projects.

If this project helps you, consider giving it a ⭐.