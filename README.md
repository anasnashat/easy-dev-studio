# Easy Dev Studio

Easy Dev Studio is a context-aware VS Code generator for Laravel, Django, Express, NestJS, and Node.js projects. This public repository distributes the tested extension package and its template-customization documentation. The source repository remains private.

## Install

Download [`easy-dev-studio-0.7.2.vsix`](./easy-dev-studio-0.7.2.vsix), then either:

1. Open VS Code.
2. Open **Extensions**.
3. Select **Views and More Actions...**.
4. Select **Install from VSIX...**.
5. Choose the downloaded package and reload VS Code.

Or install it from a terminal:

```powershell
code --install-extension easy-dev-studio-0.7.2.vsix
```

Extension ID: `AnasNashaatAhmed.easy-dev-studio`

SHA-256:

```text
B6E952136B85B5321302A3EF1A11E6501D4545802E45C43CA07F7337AFF9D713
```

## Customize generated code

Read [Template Editing Guide](./TEMPLATE_EDITING.md) for safe project-level template overrides.

AI assistants can use the included [`$easy-dev-template-editor`](./skills/easy-dev-template-editor/SKILL.md) skill.

## Supported frameworks

- Laravel
- Django and Django REST Framework
- Express
- NestJS
- Node.js

## License

MIT. See [LICENSE](./LICENSE).
