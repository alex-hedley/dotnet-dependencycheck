# Setup

DependencyCheck CLI

- https://jeremylong.github.io/DependencyCheck/dependency-check-cli/index.html

`brew install dependency-check`

> `dependency-check.sh --project "My App Name" --scan "/java/application/lib"`

> `dependency-check.sh --project "DependencyCheckExample" --scan "src/DependencyCheckExample/bin/Debug/net7.0/*.dll"`

`dependency-check --project "DependencyCheckExample" --scan "src/DependencyCheckExample/bin/Debug/net7.0/*.dll" --out "reports"`

> pwd: dotnet-dependencycheck/src

`dependency-check --project "DependencyCheckExample" --scan "DependencyCheckExample/bin/Debug/net7.0/*.dll" --out "reports"`

---

suppression-file.xml ?

Create a new file in `src`

`dependency-suppression.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<suppressions xmlns="https://jeremylong.github.io/DependencyCheck/dependency-suppression.1.3.xsd">
</suppressions>
```

Then copy the suppress content from the popup in the report.

`--suppression dependency-suppression.xml`

`dependency-check --project "DependencyCheckExample" --scan "DependencyCheckExample/bin/Debug/net7.0/*.dll" --out "reports" --suppression dependency-suppression.xml`

## Links

- [ADO](https://github.com/dependency-check/azuredevops/)

### Vulnerable

`dotnet list package --vulnerable`

```bash
dotnet list package --vulnerable --include-transitive 2>&1 | tee vuln.log
        echo "Analyze dotnet list package..."
        ! grep -q -i "has the following vulnerable packages" vuln.log
```

- https://github.com/actions/github-script

Add a **comment**.

```yml
      - uses: actions/github-script@v6
        with:
          script: |
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: '👋 Thanks for reporting!'
            })
```

If any found add a **label**?

```yml
      - uses: actions/github-script@v6
        with:
          script: |
            github.rest.issues.addLabels({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              labels: ['CVE']
            })
```
