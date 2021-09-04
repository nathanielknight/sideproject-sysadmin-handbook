# Motivation

Who is this book for?

- You're a software developer (or something adjacent to one)
- You have web-based side projects (websites, apps, etc.) that you want to publish
- You don't want to spend a whole lot of money on it, and you don't want to 
  spend extra money every time you publish something new

What this book describes:

- How to set up a VPS and a domain so that you can have a website
  at `example.com` and projects at `project1.example.com`, `project2.example.com`
  and so on.
- Automation is minimal, but things are low-level enough that you can use
  your automation tool of choice (ssh, Ansible, etc.)
- Services can run directly on the server or be run from Docker


Non-goals:

- **Automation**: This book doesn't prescribe a means of automating the tasks it
  descries. Some of them only happen infrequently, and might not be worth it to
  you to automate. Others can be easily integrated into a task runner of your
  choice (e.g. `make`). Either way, enough details tend to arise in the
  automation process that it's may not be worth it to you.
- **Hyper-scalability**: This book is for side projects that might serve a
  static site to a few thousand people or a dynamic site to a few dozen. It's
  the software equivalent of a dog house or a nice gazebo, not a multi-story
  steel-reinforced-concrete apartment building.
