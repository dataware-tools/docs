# Developers' Guides

### Description of Each Repository

| Repository                                                                         | Desription                                                                                                 |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| [dev-deps-for-apps](https://github.com/dataware-tools/dev-deps-for-apps)           | A repository for the common dev dependencies and their config files that are extended and used at each app |
| [app-common](https://github.com/dataware-tools/app-common)                         | A library of common components used across the front-end apps                                              |
| [app-launcher-next](https://github.com/dataware-tools/app-launcher-next)           | A web app for the start page                                                                               |
| [app-data-browser-next](https://github.com/dataware-tools/app-data-browser-next)   | A web app for managing and visualizing data                                                                |
| [app-user-manager](https://github.com/dataware-tools/app-user-manager)             | A web app for managing user permission on individual database                                              |
| [app-scene-viewer](https://github.com/dataware-tools/app-scene-viewer)             | A web app based on WebViz for viewing driving scenes                                                       |
| [api-helper-python](https://github.com/dataware-tools/api-helper-python)           | A library of common functions used across the back-end APIs                                                |
| [api-meta-store](https://github.com/dataware-tools/api-meta-store)                 | A set of APIs for CRUD of databases and records                                                            |
| [api-file-provider](https://github.com/dataware-tools/api-file-provider)           | A set of APIs for uploading and downloading files                                                          |
| [api-permission-manager](https://github.com/dataware-tools/api-permission-manager) | A set of APIs for managing and using user permission                                                       |
| [api-job-store](https://github.com/dataware-tools/api-job-store)                   | A set of APIs for managing jobs on the Kubernetes cluster                                                  |

### Relationship of Repositories

[https://github.com/dataware-tools/docs/blob/main/repositories-relationship.md](https://github.com/dataware-tools/docs/blob/main/repositories-relationship.md)

### Note: Using NPM Packages

Some repositories in this project use npm packages maintained under Github Packages (e.g. `app-user-manager`). You have to have completed Github's PAT (personal access token) settings to install packages under Github Packages. For more information, refer to  [Github Docs](https://docs.github.com/ja/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#authenticating-with-a-personal-access-token).
