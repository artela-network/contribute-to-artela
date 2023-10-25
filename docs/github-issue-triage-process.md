# GitHub Issue Triage Process

This document provides an overview of the current workflow for triaging issues in `contribute-to-artela` repository.

## Issue creation process

Upon the creation of a new issue, it will automatically receive the `needs-triage` label. This label indicates that the issue requires attention from the core team and should not be acted upon by anyone else to prevent unnecessary efforts. The `needs-triage` label will be removed once a core contributor has reviewed and triaged the issue.

## Triage process

The core team will review issues labeled as `needs-triage` within 5 days. In order for an issue to be considered triaged, one of the following will need to happen:

1. The issue will be closed if it is not needed, a duplicate, or spam.
2. If an issue needs more discussion, the `GH grooming` tag will be added, and the issue will be discussed next GitHub grooming. After this call, action items will be documented and the issue will be considered triaged.
3. The issue is labeled with the appropriate tags for work needed (ex: `design required`, `dev required`, etc.) and open it up for assignment. More on this below.

Once an issue has been triaged, the `needs-triage` label will be removed.

## Assignment process

After an issue has been triaged, it is ready to be assigned to someone to work on. Priority for assignment will be given in the following order:

Upon successful triage, it is ready to be assigned to someone to work on. Assignment priority follows the subsequent order:

1. A core team member
2. The person who opened the issue if they want to be assigned
3. Anyone in the community. A `help-wanted` tag will be added to the issue in this case.