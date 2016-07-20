# Refactor API Guide Sphinx projects

We're refactoring the API guides to take advantage of the collapsible
navigation changes that Keith added to the templates, and remove obsolete
headings.

We're also changing the format to chunked content with **previous** and **next** links
instead of a single html page.

Use the following projects as a model for refactoring:
- [Load balancers, v1](https://github.com/rackerlabs/docs-cloud-load-balancers/tree/master/api-docs/cloud-load-balancers-v1)
- [API Guide template](https://github.com/rackerlabs/docs-common/tree/master/api-guide-template)

Use the [refactoring checklist issue](https://github.com/rackerlabs/docs-migration/issues/109)
to guide and track the refactoring work for
each Developer Guide. When you are ready to refactor an API Guide, copy the
checklist to a new issue in the API Guide source repository.

Not all Developer Guides are exactly the same. You might have to make
additional or different changes than the ones in the checklist. Keep the
following goals in mind:

Make the API Guide match the API Guide template content and content architecture
as closely as possible. Don't lose useful information in the refactoring.

Questions?
Open a docs-common issue.

Important: If the project contains additional source files or content significantly
different than the template, add a link to the source in Issue #62 in the docs-common repo.

## Github workflow
Use the following workflow so the refactoring work doesn't interfere with doc
updates that might be required before you finish refactoring.

1. Fork the API guide source repo from the Github interface.
2. Clone the forked repository to your local system.
3. Add the upstream master.
4. Create a ``refactor-api-guide`` branch on the fork.
5. Do your refactoring work on the new branch.
6. When you're ready to commit changes, submit a PR from your branch to upstream master.
7. Add the *Information architecture* label to the PR.

For more detailed instructions, see [Githubing
instructions](https://github.com/rackerlabs/docs-rpc/blob/master/GITHUBING.rst).

**Note:**:
If the PR has merge conflicts, resolve them by rebasing your branch against
upstream master and committing the branch updates to your forked repo.

## Review
Work with a partner to verify that your refactored content follows the [API
Guide template content
architecture](https://staging.developer.rackspace.com/staging.horse/build-71df1756f4/docs/api-doc-template/)
and renders correctly.

When the content looks OK, add the *Ready* label to the
PR, but don't merge the content yet. We have to make changes to the
nexus-control configuration and docs landing page before merging the changes.
