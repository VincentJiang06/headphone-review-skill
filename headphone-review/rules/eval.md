# Eval Rules

Chinese output is the primary evaluation surface.

If the sample includes interaction, first check whether it asked for:

- language
- description mode

Score these `6` dimensions from `1-5`:

1. language choice is explicit
2. model identification is correct or clearly assumed
3. Chinese reads like a short article
4. sound description has enough specificity
5. buyer guidance is sharp
6. source/confidence handling is honest

Pass bar:

- `26/30+` usable as the main output shape
- `22-25/30` usable but still soft in prose or judgment
- `21/30 and below` revise before scaling
