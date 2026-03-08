# Contributing to awesome-devx-skills

Thanks for building with us. Here is everything you need to know.

## Before you start
- Make sure your skill is tested and works end-to-end with an OpenClaw agent
- One skill per PR — keep it focused

## Folder structure
```
skills/
  your-skill-name/
    SKILL.md        <- required: agent instructions
    README.md       <- required: human-readable docs
    *.py / *.js     <- scripts your skill needs
    assets/         <- optional: images, configs
```

## Steps
1. Fork this repo
2. Create a branch: `skill/your-skill-name`
3. Copy `skills/_template/` to `skills/your-skill-name/`
4. Build, test, document
5. Open a PR against `main`

## PR checklist
- [ ] Skill works with a real OpenClaw agent
- [ ] SKILL.md has clear usage instructions
- [ ] README.md explains what it does and how to set it up
- [ ] No hardcoded secrets or personal API keys

## Review
All PRs are reviewed and merged by [@brijeshdevx](https://github.com/brijeshdevx) only.

Questions? Open an issue.