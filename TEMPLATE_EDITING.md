# Template Editing Guide

Easy Dev Studio lets each project override bundled `.stub` templates without changing the installed extension.

## Recommended workflow

1. Open the application project in VS Code.
2. Select a framework file such as a Laravel migration, Django model, Express route, or NestJS controller.
3. Run **Easy Dev Studio: Edit Template** from the Command Palette or Explorer context menu.
4. Choose the template to customize.
5. Edit the file opened under `.easy-dev/templates/<framework>/`.
6. Generate a representative file and review the exact preview before applying it.

The command copies the correct bundled template and chooses any language-specific path for you. Prefer it over creating override paths manually.

## Template rules

- Keep the `.stub` extension.
- Preserve placeholders required by the original template, such as `{{ model }}`, `{{ class }}`, or `{{ namespace }}`.
- Do not invent placeholder names. Easy Dev Studio rejects unknown or unresolved placeholders.
- Preserve triple-brace placeholders such as `{{{ object }}}`. They protect generated values that contain template syntax, including Django template expressions.
- Keep framework syntax valid after placeholder substitution.
- For Laravel CRUD templates, do not reintroduce generated request filters or sorting blocks. Legacy filter templates are rejected.
- Change only presentation or project conventions unless the matching generator supplies the data required by deeper structural changes.

## Override locations

The normal path is:

```text
.easy-dev/templates/<framework>/<template>.stub
```

Some JavaScript templates use a language variant directory. Let **Easy Dev Studio: Edit Template** create the correct path instead of guessing it.

Overrides belong to the application project and can be committed with that project. Other projects continue using the bundled defaults.

## Validate an override

1. Generate one representative component.
2. Inspect every file in the Easy Dev Studio preview.
3. Confirm that no `{{ placeholder }}` tokens remain unexpectedly.
4. Run the generated project's formatter and tests.
5. Apply the selected files only after the preview is correct.

If an override is broken, run **Easy Dev Studio: Reset Template** to delete it and return to the bundled default.

## AI-assisted editing

Install or reference the included `easy-dev-template-editor` skill and prompt your AI assistant with a concrete target, for example:

```text
Use $easy-dev-template-editor to customize the Laravel CRUD service template so generated services follow this project's conventions.
```

Always give the AI access to the application project and ask it to validate a representative generation.
