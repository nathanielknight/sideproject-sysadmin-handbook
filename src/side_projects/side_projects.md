# Side Projects

This section describes how to set up, deploy, and otherwise administer various
kinds of side projects. It describes:

- Static sites
- Docker services (with and without persistent data)
- SystemD services

For each kind of project, it describes:

- How to deploy a **new** instance of this kind of project
- How to deploy **changes** to a project
- For projects with persistent data (e.g. Docker volumes) how to
  **take and restore backups** of that data

This section doesn't provide automation solutions for these tasks, but attempts
to describe them in enough detail that you'll be able to figure out how to
automate in the fashion and to the degree that makes sense to you.


