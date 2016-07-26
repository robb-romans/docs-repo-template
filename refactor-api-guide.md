# Refactor API Guide Sphinx projects

We're refactoring the API guides to take advantage of the collapsible
navigation updates that Keith added to the templates, remove obsolete
headings, streamline the content architecture, and adopt 
common content and boiler plate text revisions and additions.

We're also changing the format to chunked content with **previous** and
**next** links instead of a single html page.

Use the following projects as a model for refactoring:

- [API Guide template]
(https://github.com/rackerlabs/docs-common/tree/master/api-guide-template)
- [Load balancers, v1]
(https://github.com/rackerlabs/docs-cloud-load-balancers/tree/master/api-docs/cloud-load-balancers-v1)

Use the [refactoring checklist issue]
(https://github.com/rackerlabs/docs-common/issues/68)
to guide and track the refactoring work for
each API guide. When you are ready to refactor a project, copy the
checklist to a new issue in the API Guide git repository.

Not all API Guides are exactly the same. You might have to make
additional or different changes than the ones in the checklist. Keep the
following goals in mind:

- Make the rendered API Guide match the API Guide template content architecture
  and content as closely as possible. 
- Ensure that relevant content is still in the source after refactoring.

**Have questions or problems?**

If you have any questions or problems about the refactor project or instructions,
open a [docs-common issue](https://github.com/rackerlabs/docs-common/issues/new).

**Important:** If the project contains additional source files or content
significantly different than the template, add a link to the source in
[Issue #62](https://github.com/rackerlabs/docs-common/issues/62) in the docs-common repo.

## Github workflow
Use the following workflow so the refactoring work doesn't interfere with doc
updates that might be required before you finish refactoring.

1. Fork the API guide source repo from the Github interface.
2. Clone the forked repository to your local system.
3. Add the upstream master.
4. Create a ``refactor-api-guide`` branch on the fork.
5. Do your refactoring work on the new branch.
6. When you're ready to commit changes, submit a PR from your branch to
   upstream master.
7. Add the *Information architecture* and *Toolset development** labels to the PR.

For more detailed instructions, see [Githubing
instructions](https://github.com/rackerlabs/docs-rpc/blob/master/GITHUBING.rst).

**Note:**:
If the PR has merge conflicts, resolve them by rebasing your branch against
upstream master and committing the branch updates to your forked repo.

## Review

Copy the [QE checklist](https://github.com/rackerlabs/docs-common/issues/81) to a new issue
in the API documentation source repo. Have another writer use the checklist to verify that
the refactored content follows the [API
Guide template](https://staging.developer.rackspace.com/staging.horse/build-71df1756f4/docs/api-doc-template/)
and renders correctly.

When the content looks OK, add the *Ready* label to the PR, but don't merge the
content yet. We have to make changes to the nexus-control configuration and
docs landing page before merging the changes.

## Publish and deploy updates

After refactoring the API Guide, update the nexus-control configuration and the landing page to map
the refactored content and update the links on the developer.rackspace.com docs landing page. For details, 
see [issue #79](https://github.com/rackerlabs/docs-common/issues/79).


