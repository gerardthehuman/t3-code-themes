# T3 Code Themes

A collection of custom T3 Code themes. Each theme includes light and dark modes.

- [Catppuccin](themes/catppuccin.json) — Latte light and Mocha dark, with soft pastel accents.
- [GitHub](themes/github.json) — GitHub Green accents on neutral surfaces.
- [GitHub Copilot](themes/github-copilot.json) — Copilot purple accents.
- [GitHub Security](themes/github-security.json) — Security blue accents with green details.

## Installation

Ask your agent:

```text
Help me install the T3 Code themes from this repository: https://github.com/gerardthehuman/t3-code-themes
```

Or install a theme manually:

1. Open the theme's JSON file above and copy its contents.
2. Create the directory `~/.t3/userdata/themes/` if it does not exist.
3. Create a file in that directory with the theme ID as its name, such as `github.json`.
4. Paste the copied JSON into the file and save it.
5. Select the theme in **Settings → Appearance**.

## Creating Your Own

Install the [create-t3-code-theme skill](skills/create-t3-code-theme/SKILL.md) to create themes with your agent:

```sh
npx skills add gerardthehuman/t3-code-themes --skill create-t3-code-theme
```

Then ask your agent:

```text
Use the create-t3-code-theme skill to create a [brand or palette] theme with light and dark modes. Save it in this project's themes/ folder.
```
