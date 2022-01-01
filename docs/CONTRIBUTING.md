# Contributing Guide
This guide will provide an overview of the procedures and workflow used to collaborate on the content being developed within this projects. It will provide an overview of the repository structure, provide instructions on opening issues, forking the repository, creating content and pull requests and explain the templates we are using to standardise the content being developed.

Use the table of contents icon <img src="../assets/images/table-of-contents.png" width="25" height="25" /> on the top left corner of this documents to get to a specific section of this guide quickly.

## Getting Started
This repository contains the working content for the documentation and certification of the draft Alignment based Reference View (Model View Definition) or AbRV for the reference exchange of infrastructure information.

It also serves as an initial proof of concept for the use of a git repository for the development and dissemination of MVD certification information, with the objective to speed up the development of the certification test cases and content, and provide greater access and readability of the certification critieria content.

The repository is structured into the following layers breaking down the content in to the MVD exchange definitions and associated Test cases & Test case datasets:

- **Repository**: the Alignment based Reference View
  - *Readme*: Documentation of the MVD
  - **AbRV Exchange Definitions**: one **folder** per defined exchange
    - *Readme*: Documentation of the exchange definition
    - **Individual Test Cases**: one **folder** per defined test case
      - *Readme*: Documentation of the Test case
      - **Test Case Dataset**
        - *Readme*: Documentation of the test case dataset
        - IFC dataset, images, and supplimentary files

The content of the readme's and folders is further explained below in the [templates](#templates) section of the guide.

## Issues & Proposals
If you spot an problem or have a proposal for additional content such as exchange definitions or test cases, this should be logged as an issue. Before logging a new issue make sure to [search if an issue already exists](https://docs.github.com/en/github/searching-for-information-on-github/searching-on-github/searching-issues-and-pull-requests#search-by-the-title-body-or-comments), to avoid duplication. If a related issue or proposal doesn't exist, you can open a new issue using a relevent [issue form](https://github.com/bSI-InfraRoom/MVD-Infra-Test-Instructions/issues/new/choose).

Please label your issues appropriately using the currently defined labels of the repository. Labels are based on the catagory of issue and the effect a solution will have on the content base.

## Content Contribution
To contribute to the content being developed or solve outstanding issues brought up by the community, this repository uses a Fork & Pull Request workflow to ensure quality and control contribution to the content base.

### Forking & Branches
First step to contributing is to [Fork](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/working-with-forks) this repository. Once this is complete you are free to create a 'Feature' branch(es) for the content you are developing. Please keep the scope of your branch (and therefore your submission) as concise as possible e.g. one exchange definition, one (or even just a part of a) test case or one bug fix. this speeds up development and quality assurance of the content.

The repository has 2 main branches:
- master: containing primary released content
- develop: completed and/or quality assured content for the next release.

feature branches should be named `feature/xxxx` to destinguish them from other types of branches such as bugfixes or release branches.

### Content & Templates
Once a fork and branch has been setup, you are free to develop your content. this should be developed using the templates in the [docs](./) folder for an exchange definition or test case. detailed content of the readme's and folders is further explained below in the [templates](#templates) section of the guide.

### Pull Requests
once the content is complete or is ready to be initially reviewed by the maintainers, please create a [pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork) to the `develop` branch of this repository. feel free to use the draft setting to notify us of developing work, but is not yet ready for review.

use the provide pull request template to specify the content being submitted and assign the appropriate labels. Assignees are those developing the pull request (aka you!) and Reviewers will be assigned appropriately based on content.

Make sure to Link the relevent issue to your pull request via the Linked issues interface or key words such as `fixes #XX` in the PR summary. [Information on linking issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue).


## Templates

TBC