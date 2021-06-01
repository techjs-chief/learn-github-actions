# Create an example workflow
GitHub Actions uses YAML syntax to define the events, jobs, and steps. These YAML files are stored in your code repository, in a directory called .github/workflows.

You can create an example workflow in your repository that automatically triggers a series of commands whenever code is pushed. In this workflow, GitHub Actions checks out the pushed code, installs the software dependencies, and runs bats -v.

1. In your repository, create the .github/workflows/ directory to store your workflow files.
2. In the .github/workflows/ directory, create a new file called learn-github-actions.yml and add the following code.
    ```
    name: learn-github-actions
    on: [push]
    jobs:
    check-bats-version:
        runs-on: ubuntu-latest
        steps:
        - uses: actions/checkout@v2
        - uses: actions/setup-node@v1
        - run: npm install -g bats
        - run: bats -v
    ```
3. Commit these changes and push them to your GitHub repository.