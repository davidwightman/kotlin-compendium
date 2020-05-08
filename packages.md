## Packages

### Packages
- a way to group related code together
- files, function and packages
- a package definition is the first line of a file
```
package com.organisation.project.configuration
```
- practically, a package is a folder on the disk
- scope (visibility) within the same package
- in order to use code from another package, that package must be imported into the project

### Naming Covention for Packages
- package names are seperated by dots
- names are always lower case, with no underscores
- leftmost name is the highest level package
- rightmost name is the lowest level package

### Imports
- In order to use code from another package, that code must be imported into the project
- Imports go at the top of the file, after the package declaratioin
- import package.* will import all functions from that file