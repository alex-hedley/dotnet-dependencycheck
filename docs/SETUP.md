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

## Links

- [ADO](https://github.com/dependency-check/azuredevops/)
