# External Tools

The tools in this directory are for use with GitHub.com (rackerlabs) for
external documentation.

Our external documentation system is deconst deploying to two Rackspace sites.
Deconst is an open-source end-to-end documentation delivery system built by a
former Racker.

## Workflow

In an external repo already set up with deconst, the process for publication is
simple.

1.  Make changes to documentation in a new branch (not `master` or `gh-pages`)
    OR make changes in your fork/clone of the repo.

1.  Open a PR on `master`.

1.  Wait for deconst to post a status update to your PR. You will see a green
    check mark and a comment with a staging link if the PR passes. You will see
    a red X if the PR fails.

    1.  If the PR passes, check out staging to ensure everything looks fine.
    1.  If the PR fails, use the `Details` link to see where the build failed.

1.  Once the PR passes and staging looks fine, request a review from an IX team
    member.

    1.  If there are any comments, resolve them.
    1.  If the PR is merged, Jenkins builds and deploys the page to the
        website.

## Under the Hood

Deconst is a set of Docker containers that interact to build and present a
static site. Among the relevant containers, there is a container that runs
Strider CI/CD, a continuous integration/continuous delivery (CI/CD) system, and
another that runs a MongoDB database. For a more detailed view of deconst's
architecture, see the deconst documentation's
[Architecture section]
(http://deconst-docs-rtd.readthedocs.io/en/latest/developing/architecture.html).

Strider conducts the entire deconst process from building and staging PRs to
deploying to the support.rack and dev.rack websites.

## Use

First, add the `RackerNexus` service account as an admin collaborator on your
repo. Notify the [IX tools team](mailto:devdocs@rackspace.com) that you have a
new repository to add to deconst so they know to go accept the invitation to
your repo on the service account.

After the RackerNexus user accepts the invitation, take the files from this
directory, and put them in the root of your repo. Replace the following lines
in the different files to match your repo.

### RST

### Markdown

### RAML

Coming soon
