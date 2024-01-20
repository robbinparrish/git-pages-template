## Disclaimer.
The content on this account/repository provided solely for educational and informational purposes.
It is not intended for use in making any kind of business, investment and/or legal decisions.
Although every effort has been made to keep the information up-to-date and accurate, no representations and/or warranties, express and/or implied, completeness, accuracy, reliability, suitability, and/or availability of the content.

## Git Pages Template.
This Project contains template for hosting Git pages. The documentation is generated using [mkdocs](https://www.mkdocs.org/).  
Once the documentation is generated it can easily published either on [GitLab Pages](https://docs.gitlab.com/ee/user/project/pages/) or [Github Pages](https://docs.github.com/en/pages).

## Project Template.
This project uses [poetry](https://python-poetry.org/docs/) to manage dependencies. The below commands can be used to manage dependencies.
```bash
# Add any new dependency package.
poetry add package-name

# Remove any dependency package.
poetry remove package-name

# Update packages.
poetry update
```

This project uses [mkdocs](https://www.mkdocs.org/) for generating documentation. The below commands can be used to interact with mkdocs.
```bash
# The initial project created for this repository using below command.
poetry run mkdocs new .

# Start the mkdocs server.
poetry run mkdocs serve

# Build the documentation site.
poetry run mkdocs build
```

## Interacting with GitLab CI Pipeline.
This repository also contains a `.gitlab-ci.yml` file for building the documentation using mkdocs in GitLab CI Pipeline.  
[.gitlab-ci.yml](https://docs.gitlab.com/ee/ci/yaml/)

### Prerequisite.
Following variables in the CI environment must be available to publish the Pages in GitLab CI.

#### Predefined environment variables.
These can be found at [GitLab Predefined Variables](https://docs.gitlab.com/ee/ci/variables/predefined_variables.html)

##### Additional variables.
This required to create a tag using GitLab CI.

- PROJECT_ACCESS_TOKEN

#### Custom environment variables.
These are specific to the needs.

## Interacting with GitHub CI Pipeline.
This repository also contains a `.github/workflows` directory for building the documentation using mkdocs in GitHub actions. `Currently Not Configured for main branch.`  
[GitHub actions](https://docs.github.com/en/actions)
