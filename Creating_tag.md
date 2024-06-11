<!--markdownlint-disable MD041-->
### I want to be safe when creating the tag for the target file , I'd like to follow the procedure below ###

Recommended/Alternate way to use Git tags
In this method, We will create a branch from a tag and then checkout the branch. The below-given command will create a new branch wherein a git tag is created. Remember, you have to create a tag locally prior to mentioning it in the below command. However, branch you are writing in below command should not be created prior to implementing this command. A new branch is created in this command.

Could you help me creating a step by step guide to have success on creating a tag?

### Step-by-Step Guide to Creating a Tag and Branch ###

Step 1: Create a Tag Locally

1- Make sure your working directory is clean: Ensure you have committed all your changes.

```bash
git status
```

2- Create a new tag: Replace *tagname* with your desired tag name (e.g., v1.0.0).

```bash
git tag tagname
```

3 - Push the tag to the remote repository:

```bash
git push origin <tagname>
```

Step 2: Create a Branch from the Tag

1- Create and checkout a new branch from the tag: Replace *tagname* with your tag name and new-branch-name with your desired branch name.

```bash
git checkout -b <new-branch-name> <tagname>
```

2 - Push the new branch to the remote repository:

```bash
git push origin <new-branch-name>
```

#### Example - Creating a Tag and Branch ####

Here’s an example workflow using specific names:

1 - Create and push a tag named v1.0.0:

```bash
git tag v1.0.0
```

```bash
git push origin v1.0.0
```

2 - Create and checkout a new branch named release-v1.0.0 from the tag v1.0.0:

```bash
git checkout -b release-v1.0.0 v1.0.0
```

3 - Push the new branch to the remote repository:

```bash
git push origin release-v1.0.0
```

Detailed Steps and Commands

1 - Ensure your working directory is clean:

```bash
git status
```

If there are any changes, commit them:

```bash
git add .
git commit -m "Your commit message"
```

2 - Create a new tag:

```bash
git tag v1.0.0
```

3 - Push the tag to the remote repository:

```bash
git push origin v1.0.0
```

4 - Create and checkout a new branch from the tag:

```bash
git checkout -b release-v1.0.0 v1.0.0
```

5 - Push the new branch to the remote repository:

```bash
git push origin release-v1.0.0
```

Verification

1 - Check the tags:

```bash
git tag
```

> You should see v1.0.0 in the list.

2 - Check the branches:

```bash
git branch
```

> You should see release-v1.0.0 in the list.

3 - Verify the branches on the remote repository:

```bash
git branch -r
```

> You should see origin/release-v1.0.0 in the list.

By following these steps, you will create a tag and a new branch from that tag safely.

### Step-by-Step Guide to Creating an Annotated Tag and Branch ###

Step 1: Create an Annotated Tag Locally

1 - Make sure your working directory is clean: Ensure you have committed all your changes.

```bash
git status
```

2 - Create an annotated tag: Replace *tagname* with your desired tag name (e.g., v1.0.0) and provide a message.

```bash
git tag -a <tagname> -m "Your tag message"
```

3 - Push the annotated tag to the remote repository:

```bash
git push origin <tagname>
```

Step 2: Create a Branch from the Tag

1 - Create and checkout a new branch from the annotated tag: Replace *tagname* with your tag name and *new-branch-name* with your desired branch name.

```bash
git checkout -b <new-branch-name> <tagname>
```

2 - Push the new branch to the remote repository:

```bash
git push origin <new-branch-name>
```

#### Example - Creating an Annotated Tag and Branch ####

Here’s an example workflow using specific names:

1 - Create and push an annotated tag named v1.0.0:

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin v1.0.0
```

2 - Create and checkout a new branch named release-v1.0.0 from the tag v1.0.0:

```bash
git checkout -b release-v1.0.0 v1.0.0
```

3 - Push the new branch to the remote repository:

```bash
git push origin release-v1.0.0
```

#### Detailed Steps and Commands ####

Ensure your working directory is clean:

```bash
git status
```

If there are any changes, commit them:

```bash
git add .
git commit -m "Your commit message"
```

Create an annotated tag:

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
```

Push the annotated tag to the remote repository:

```bash
git push origin v1.0.0
```

Create and checkout a new branch from the tag:

```bash
git checkout -b release-v1.0.0 v1.0.0
```

Push the new branch to the remote repository:

```bash
git push origin release-v1.0.0
```

#### Verification ####

Check the tags:

```bash
git tag
```

> You should see v1.0.0 in the list.

Check the branches:

```bash
git branch
```

> You should see release-v1.0.0 in the list.

Verify the branches on the remote repository:

```bash
git branch -r
```

> You should see origin/release-v1.0.0 in the list.

By following these steps, you will create an annotated tag and a new branch from that tag safely.

#### Reading about this process I saw the following recommendation: After pushing tags to the remote repository, the user has to navigate to GitHub and on the left hand side of your remote repository, there is an updation that a new tag is created. Click on that tab and publish your latest release.Only after publishing the tag, a separate new version of your code will be created ####

*This recommendation is about creating a GitHub release based on the tag you have pushed. A GitHub release is a more formal way of distributing your code, as it allows you to attach binaries and provide detailed release notes.*

Here's a step-by-step guide on how to do this:

### Step-by-Step Guide to Creating a Tag, Branch, and GitHub Release ###

Step 1: Create an Annotated Tag Locally

Ensure your working directory is clean:

```bash
git status
```

If there are any changes, commit them:

```bash
git add .
git commit -m "Your commit message"
```

Create an annotated tag:

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
```

Push the annotated tag to the remote repository:

```bash
git push origin v1.0.0
```

Step 2: Create a Branch from the Tag

Create and checkout a new branch from the tag:

```bash
git checkout -b release-v1.0.0 v1.0.0
```

Push the new branch to the remote repository:

```bash
git push origin release-v1.0.0
```

Step 3: Publish the Release on

Navigate to your repository on GitHub.

On the left-hand side, click on the "Releases" tab.

You should see an update that a new tag (v1.0.0) is created. Click on the "Draft a new release" button.

Fill in the release details:

Tag version: Select the tag you created (v1.0.0).

Release title: Give your release a title (e.g., "Release version 1.0.0").

Description: Provide a description of the release. You can include details about what’s new, fixed, or improved.

Attach binaries or other files (optional): If you have any compiled binaries or other files to include in the release, you can attach them here.

Publish the release: Click on the "Publish release" button.

#### Example - Create and push an annotated tag named v1.0.0 ####

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin v1.0.0
```

Create and checkout a new branch named release-v1.0.0 from the tag v1.0.0:

```bash
git checkout -b release-v1.0.0 v1.0.0
git push origin release-v1.0.0
```

Publish the release on GitHub:

Navigate to your repository on GitHub.

Click on the "Releases" tab.

Click on "Draft a new release".

Select the tag v1.0.0.

Fill in the release title and description.

Attach any files (optional).

Click on "Publish release".

Summary
By following these steps, you will create an annotated tag, a branch from that tag, and publish a release on GitHub. This makes it easy to distribute your code and binaries, and provides a clear version history for your project.
