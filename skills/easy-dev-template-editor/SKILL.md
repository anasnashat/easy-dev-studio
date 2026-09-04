---
name: easy-dev-template-editor
description: Safely customize Easy Dev Studio .stub templates for Laravel, Django, Express, NestJS, or Node.js generated output. Use for project template overrides or intentional bundled-template changes; do not use merely to edit already-generated application files.
---

# Easy Dev Studio Template Editor

Customize generated output while preserving the extension's rendering contract.

## Choose the target

Default to a project override. Run **Easy Dev Studio: Edit Template** and edit the resulting file under `.easy-dev/templates/<framework>/`. Modify bundled templates under `resources/templates/` only when the user explicitly asks to change the extension itself.

Inspect the original stub and the generator that renders it before editing. Reuse existing conventions and variables.

## Preserve rendering invariants

- Keep the `.stub` extension and framework-valid syntax.
- Preserve required placeholders and their exact names.
- Do not invent a placeholder unless the corresponding generator supplies it on every rendering path.
- Preserve triple-brace placeholders such as `{{{ object }}}`; they protect inserted values containing template syntax from the unresolved-variable check.
- Do not move an override outside `.easy-dev/templates/`.
- Do not add Laravel request filtering or sorting boilerplate to CRUD templates; legacy filter overrides are intentionally rejected.
- Keep generated classes extensible unless the user explicitly requests `final` classes.

When changing a bundled template, search every renderer and test that references its template type. Update implementation and its focused tests together.

## Validate

For a project override, generate one representative component, inspect the Easy Dev Studio diff preview, and run the target project's relevant formatter or test command when available.

For bundled extension templates, run:

```powershell
npm test
npx @vscode/vsce package
```

Reject the change if generation reports `UNRESOLVED_TEMPLATE_VARIABLES`, produces unexpected remaining placeholders, overwrites unrelated files, or emits invalid framework syntax.

Use **Easy Dev Studio: Reset Template** to restore a broken project override.
