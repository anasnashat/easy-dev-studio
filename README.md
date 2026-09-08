# Easy Dev Studio

Easy Dev Studio is a context-aware VS Code generator for Laravel, Django, Express, NestJS, and Node.js projects. This public repository distributes the tested extension package and its template-customization documentation. The source repository remains private.

## Install

[Install Easy Dev Studio from the Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=AnasNashaatAhmed.easy-dev-studio), or use:

```powershell
code --install-extension AnasNashaatAhmed.easy-dev-studio
```

For manual installation, download [`easy-dev-studio-0.7.3.vsix`](./easy-dev-studio-0.7.3.vsix), then:

1. Open VS Code.
2. Open **Extensions**.
3. Select **Views and More Actions...**.
4. Select **Install from VSIX...**.
5. Choose the downloaded package and reload VS Code.

Or install it from a terminal:

```powershell
code --install-extension easy-dev-studio-0.7.3.vsix
```

Extension ID: `AnasNashaatAhmed.easy-dev-studio`

SHA-256:

```text
455FE812257CA0A01FEB731E152C1491F17516A89E124374C0EC6D18876606E6
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
