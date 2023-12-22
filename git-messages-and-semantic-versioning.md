# Git Commit Message & Semantic Versioning
[SemVer](https://semver.org/)
[Conventional Commits](https://www.conventionalcommits.org/)

## Version Numbers
Given a version number MAJOR.MINOR.PATCH, increment the:

- MAJOR version when you make incompatible API changes
- MINOR version when you add functionality in a backward compatible manner
- PATCH version when you make backward compatible bug fixes
Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

e.g. `Product: 9.12.2`

---
## Commit Messages
The commit message should be structured as follows:

```plaintext
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Type
- **fix:** a commit of the type `fix` patches a bug in your codebase (this correlates with *PATCH* in Semantic Versioning).
- **feat:** a commit of the type `feat` introduces a new feature to the codebase (this correlates with *MINOR* in Semantic Versioning).
- build:
- docs:
- style:
- refactor:
- chore:
- ci:
- perf:

### Scope
A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., `feat(parser): add ability to parse arrays.`


### Breaking Change
A commit that has a footer `BREAKING CHANGE:`, or appends a `!` after the type/scope, introduces a breaking API change (correlating with MAJOR in Semantic Versioning). A BREAKING CHANGE can be part of commits of any type.

### Footers
Other than `BREAKING CHANGE: <description>` may be provided and follow a convention similar to [git trailer format](https://git-scm.com/docs/git-interpret-trailers.

### ClickUp + BitBucket
ClickUp will automatically pick up any new activity and associate it with tasks.

Add a ClickUp task ID in any part of the pull request title, branch name, or commit message in one of these formats:

- `#{task_id}`
- `CU-{task_id}`
- `{custom_task_id}`

For example:
- `#1abc2de`
- `CU-1abc2de`
- `prefix-1`

#### Automatically change task status
Add the ClickUp task ID in any part of the commit message, as well as the status you want inside brackets.
For example: `#ud5b[ready]`

### Examples
#### Message with `!` to draw attention to breaking change in footer
```plaintext
feat!: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

#### No body 
```plaintext
docs: correct spelling of CHANGELOG
```

#### Message with scope
```plaintext
feat(lang): add Polish language
```

#### Long message with multi-paragraph body and multiple footers
```plaintext
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

With: Alice <alice@example.com>
Reviewed-by: Bob <bob@example.com>
Resolves #abc123[done]
```
