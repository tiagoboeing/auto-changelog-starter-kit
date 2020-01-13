# auto-changelog-starter-kit

This project is a starter kit with [auto-changelog](https://www.npmjs.com/package/auto-changelog) dependency configurated. Pre-integrated with [ClickUp](https://app.clickup.com/).

- For manual installation or tips:
  - [PT-BR](https://medium.com/@tiagoboeing/automatizando-gera%C3%A7%C3%A3o-de-changelogs-em-seus-projetos-nodejs-a4d2300c49d3)
  - [English](https://medium.com/@tiagoboeing/automating-changelog-in-your-nodejs-project-c54bdbb56e57)
- Original dependency: [auto-changelog](https://www.npmjs.com/package/auto-changelog)

# Result

![](https://miro.medium.com/max/1184/1*ABit6gC--YP_oETQwjhi7w.png)

The generated changelog includes three sections if apply.

The line generated: `#TASK_ID - Commit Message (#COMMMIT_SHA)`

## How to use

### Available sections

- `fix:` - for hotfix, bugfix and others
- `break:` - for breaking changes
- `feature:` - for features in your app

### Commit message

Choose and include section id in your commit message.

Examples:

- `fix: #TASK_ID_CLICKUP Created changelog for app` 
- `feature: #TASK_ID_CLICKUP Created changelog for app` 
- `break: #TASK_ID_CLICKUP Created changelog for app` 
- `fix: Created changelog for app` - without task id

# I use Jira

No problem, in your `package.json` change the property `auto-changelog` for:

```
"auto-changelog": {
    "commitLimit": false,
    "unreleased": true,
    "issueUrl": "http://jira.user.com.br/browse/{id}",
    "replaceText": {
      "[Ff]eature:": "",
      "[Ff]ix:": "",
      "[Bb]reak:": "",
      "([A-Z]+-\\d+)": "[$1](http://jira.user.com.br/browse/$1) - "
    },
    "includeBranch": [
      "develop",
      "master"
    ]
}
```
