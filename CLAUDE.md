# CLAUDE.md

## `.temp` folder

- `.temp` is the repository's local working folder for temporary and large files, e.g. dumps, exports and installation working files
- `.temp` is listed in `.gitignore`, so its contents are never committed and are not included in a clone
- `.temp` can be a regular folder or a symlink to another disk. Do not replace a symlink with a regular folder. If the link appears broken, its target disk is not mounted
- If `.temp` is missing, create it in the repository root and make sure `.gitignore` contains the line `.temp` (`.temp/` alone does not match a symlink)
