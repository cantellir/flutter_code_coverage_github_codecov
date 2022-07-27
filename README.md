[![codecov](https://codecov.io/gh/cantellir/flutter_code_coverage_github_codecov/branch/main/graph/badge.svg)](https://codecov.io/gh/cantellir/flutter_code_coverage_github_codecov)

# Flutter code coverage integration between Github and Codecov

A Flutter project demonstrating how to integrate github actions with [Codecov](https://about.codecov.io/) analysis tool;

## How to setup your own project?

- Login to Codecov with an account on Github, Gitlab or Bitbucket;
- Select a repository that is not yet configured;
- If the repository is private, copy the token and add it to the github repository secrets:
  - In your github repository go to settings > Secrets > Actions > New repository secret;
- Add a new step in the github workflow (the last step of this repository workflow);
  - Add token line below file line if repository is private: ```token: ${{ secrets.NAME_OF_SECRET }}```
- On the next pull request/commit on the main branch, coverage will be sent to Codecov.

## How it works?

- The step ```Run generate coverage``` in the yaml test-code-coverage job run tests and generate coverage report file (```lcov.info```);
- In the final step, the action gets generated report file and sends it to codecov.

## Additional info

This is the fourth part of four repositories teaching how to handle code coverage in Flutter APPs:

[Part 1 - Flutter code coverage in a single package app](https://github.com/cantellir/flutter_code_coverage_single_package);

[Part 2 - Flutter code coverage in a multi package app](https://github.com/cantellir/flutter_code_coverage_multi_package);

[Part 3 - Github actions to handle Flutter APP minimum coverage](https://github.com/cantellir/flutter_code_coverage_minimum_github_action);

[Part 4 - Integration with Codecov analysis tool](https://github.com/cantellir/flutter_code_coverage_github_codecov);