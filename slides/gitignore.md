### .gitignore

A versioned file that excludes files from the repo

```sh
# Exclude these files from the repo:

node_modules/
vendor/
*.log
*.sql
```

Note:

* Exclude code loaded via dependencies (node_modules, vendor, etc.)
* More code excluded == less code to be checked and reviewed
* Omit compiled assets if you're able to leverage build scripts or a CI/CD pipeline
