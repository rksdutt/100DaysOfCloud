---
title: "Simplify Code-Pipeline With GitHub Action⚒️"
datePublished: Sun Aug 04 2024 14:28:12 GMT+0000 (Coordinated Universal Time)
cuid: clzfnqlrs000408jvc6vb77hp
slug: what-is-github-action
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1722785229448/7f49cdb8-9004-411a-a24a-af921f3d8fdc.jpeg
tags: github, github-actions-1, remotereposittory

---

GitHub Actions is a tool that helps automate our development workflow. It lets us set up automated processes for building, testing, and deploying our code. Whenever something happens in our code repository like a new commit or a pull request GitHub Actions can trigger custom workflows. It uses Docker containers to run our code and works with any programming language whether we're on public clouds or local servers. This is just one part of a series on continuous integration and delivery (CI/CD).

### How GitHub Action Works !!

GitHub Actions is built right into GitHub. It uses workflows, which are saved in our repository’s .github/workflows/ folder. These workflows start automatically when something happens in our repo like a pull request or a commit or from external triggers using webhooks. Once a workflow is triggered a runner takes over and running jobs one at a time. Each job is made up of steps which include actions that perform specific tasks in the workflow.

### Components of GitHub Action

When something happens in our repository like opening a pull request or creating an issue GitHub Actions can automatically start. The workflow then runs one or more jobs which can be done one after the other or at the same time.

**Workflows**

A GitHub Actions workflow is a set of instructions that automates tasks in your project. We create and store these instructions in a YAML file within the .github/workflows/ directory of your repository. This file can trigger workflows in three ways when a specific event happens in the repo (like a pull request or code change) manually or on a set schedule.

You can have multiple workflows to handle different tasks, such as building and testing code, deploying updates, or managing issues. For example, one workflow might test code for every pull request while another deploys your code to production once tests pass. This setup keeps your development process automated and efficient! 🚀📦

**Events**

An event is what starts a GitHub Actions workflow. This could be something like pushing a commit or creating a pull request or even an external trigger like a repository dispatch webhook. Events are what get the automated pipeline rolling whether they're specific actions within our repository or external signals like scheduled triggers or manual commands. For example, a commit push or a PR creation can set off a workflow helping automate and streamline our development process.

**Jobs**

A job in GitHub Actions is a collection of steps that run on the same runner. By default jobs execute in parallel but you can set them to run sequentially if needed. We can group related tasks into one or more jobs organizing them in the order we can define. Our workflow can include jobs that run simultaneously in sequence or a mix of both. For example, suppose we have several build jobs running in parallel for different chip architectures and once they all finish a separate job could handle packaging the builds. We can also set up dependencies between jobs to manage their execution flow.

**Steps**

A step in GitHub Actions is a single task within a job that runs commands or actions. Each step executes on the same runner so it can easily share data with other steps in that job. Steps are the building blocks of a job allowing us to define and sequence the tasks that need to be completed. This setup ensures smooth coordination and data flow between tasks in our workflow.

**Actions**

Actions are the smallest units in a GitHub Actions workflow. They are standalone commands that perform specific tasks and can be used across multiple workflows.We can create our own actions or use ones from the GitHub community.

While individual steps in a job might be simple shell scripts actions are more complex and can interact with our GitHub repository or external APIs. They can do things like deploy code or send alerts and can be run inside Docker containers if needed. Actions are reusable and can be referenced in our workflow YAML files which making them a powerful way to streamline and standardize tasks. We can also explore a wide range of free, open-source actions in the GitHub Actions marketplace or contribute our own.

**Runners**

A runner is a server or agent that executes jobs in a GitHub Actions workflow. It listens for available jobs runs them one at a time and sends progress, logs and results back to GitHub. GitHub provides hosted runners with virtual machines running Ubuntu Linux, Microsoft Windows or macOS for our tasks. If we need specific hardware or an operating system not offered by GitHub we can set up our own runner. Each job gets its own runner, ensuring isolated and fresh environments for every task.

### Does GitHub Action really worthy or Jenkins is better !!

The integration feature with GitHub means that developers can manage their CI/CD pipelines right from the place they use for version control. GitHub Actions has a simplified configuration setup compared to Jenkins since it uses YAML based configuration files.

**Advantages of GitHub Actions**

**Beginner-friendly :** Easy to use with just one YAML file to set up the workflow. Ideal for them already familiar with YAML.

**Managed Runners :** Offers free managed runners so we don't need to maintain our own server. We can add self hosted runners if needed.

**Integrated with GitHub :** Integrated directly into GitHub making it seamless for projects hosted there.

**Disadvantages of GitHub Actions**

**Platform limitations :** Tied to GitHub so it doesn't support other code hosting platforms like GitHub or Bitbucket.

Limited Features : As a new tool GitHub Actions may lack some of the advanced features and integrations that Jenkins offers.

Overall, A GitHub Actions workflow is a set of instructions written in a YAML file stored in the .github/workflows/ folder of our repo. It automates tasks and can be triggered automatically by events (like a pull request), manually or on a schedule. We can create multiple workflows for different tasks like testing code or deploying updates making our development process more efficient and streamlined.