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
