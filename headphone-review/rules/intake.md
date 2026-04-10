# Intake Rules

Ask the missing preferences before you review:

- `你想要中文还是英文输出？`
- `你想要更客观的描述，还是更情绪化、抽象一些的描述？`

Normalize answers into:

- `中文` or `English`
- `客观` or `情绪化抽象`

Do not ask again if the user already made the choice.

Model lock:

- Normalize to `brand + model + revision/form factor`.
- If the name is ambiguous, choose the most likely current meaning and mark the assumption in the report.
- Common traps: `Dusk`, `Xelento`, `QuietComfort Ultra`, `Utopia`.
