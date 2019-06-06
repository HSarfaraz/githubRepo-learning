I'm giving you the instructions below simply to get you up and
running.  Bear with me.

They're for Eclipse version 2019-03.  They will probably vary for
older versions of Eclipse but hopefully not too much.

Keep in mind I actually don't know very much about Eclipse and I had
to spend quite a bit of time going through this process myself to make
sure I could give you instructions that would work.

Because you're on holiday tomorrow and I'm getting cataract surgery
Thursday, we'll talk Friday if you have any questions.

I expect you to read all of the instructions below, and read them
carefully.  You may skip to them now and read the rest of this later.

Don't type the backticks ``.

> The only reason I didn't want you messing with git bash is I didn't
> feel at the time that a command line environment was appropriate for
> a sudden crash course in branching in git.
>
> However in the long term a command line environment really is best.
> You installed Git Bash and it will be fine.  Please spend a little
> time learning the basics of GNU Bash, then read the first few
> chapters of [Pro Git](https://git-scm.com/book/en/v2) which you can
> read online at no cost.  The stuff about branching is especially
> important.
>
> That book *does* expect you to know how to use the command line.
> And most people you work with may also expect you to know how to use
> it.  And I can guarantee that you're *going* to work with Git based
> projects later on in your career.  And instructions are **really**
> hard and verbose to write correctly for GUIs.

Instructions are as follows:

0.  I'm going to assume you made your changes in the master branch in
    your project.  You should not have, but as long as you didn't PUSH
    them, don't worry, and DO keep your existing project.

1.  I need you to create a *new* project with a *new* clone of the Git
    repository.  You'll create a branch in it, check out that branch,
    and make your changes in that branch.

    Here's how, in case you don't know:

    -   Select: File -> Import
    -   A dialog will open up.  Select: Git -> Projects from Git.
    -   Select: Clone URI.
    -   Enter the Git project URI and your credentials in the
        appropriate fields.  Click Next.
    -   Leave all branches selected.  Click Next.
    -   In Local Destination, leave everything as-is and click Next.
    -   Eclipse will take a few seconds to clone the Git repository
        into your local destination.
    -   Then you'll be able to select a wizard.  Select "Import as
        general project" and click Next.
    -   You can keep the project name or change it.  Then click
        Finish.

    In Project Explorer, the project name should say something like:

    ```
    <your project name> [gea-schedule-service-2018 master]
    ```

    This indicates you're checked in the `master` branch after having
    created it.

2.  The reason I had you create a new project, with a new clone of the
    repository, is that you need to create a developer branch for
    yourself FIRST, check out that branch, then make your changes IN
    THAT BRANCH.

    Here's how to create the branch and check it out:

    -   Right-click on that project name.  The pop-up menu may take a
        few seconds to show up, but it will show up.
    -   Select: Team -> Switch To -> New Branch.
    -   In the branch name field, type: `developer/firstname-lastname`
        -   Example: `developer/darren-embry`
        -   Note: all lowercase, please
    -   Make sure "Configure upstream for push and pull" is NOT
        checked.
    -   Make sure "Check out new branch" IS checked.
    -   Click Finish.

    Project name in Project Explorer should say something like:

    ```
    <your project name> [gea-schedule-service-2018 developer/firstname-lastname]
    ```

    indicating you're checked out into your new branch.

3.  Make your changes or copy your changes from the existing project
    to this one.  Whatever you need to do.  Save them.

4.  Right-click your project name, select Team -> Commit.

    A new window pane will open up, with a tab called "Git Staging"
    selected, and a few other tabs.

    -   You'll see a box for **Unstaged Changes**.  Those changes will
        not be committed.
    -   You'll see a box for **Staged Changes**.  Those changes WILL
        be committed.
    -   Move files between those two boxes as needed.
    -   You'll see a box for **Commit Message**.  Type in a
        description of your changes there.
        -   First line should contain a one-line summary.  Preferably,
            less than 72 characters.
        -   Second line should be blank.
        -   Third line onwards should contain details, if needed.
    -   Click "Commit and Push".

5.  Your changes should be in the remote repository, in your new
    branch, now.

6.  **To view your changes in GitHub Pages**:

    -   Right-click your project; select Team -> Switch To -> Other.
    -   Select Remote Tracking -> `origin/gh-pages`.
    -   Click "Check Out".
    -   You'll be shown with a dialog, select "Check out as New Local Branch".
    -   In the "Create a New Branch" dialog, leave everything as-is and click Finish.

    Your project name under Project Explorer should indicate that
    you're checked out into the `gh-pages` branch now.

    -   Select Team -> Merge.
    -   A new dialog will open up, titled "Merge 'gh-pages'".
    -   It will say, "Select a branch or tag to merge into the gh-pages branch."
        Read that carefully, just so you understand what that means.
    -   Select your developer branch under Local, i.e., Local -> `developer/firstname-lastname`.
    -   Leave everything else as-is and click Merge.
    -   You'll see a dialog entitled "Merge Result".
    -   You should be able to just click "OK" in it.

    Your project name should look something like:

    ```
    <your project name> [gea-schedule-service-2018 gh-pages ↑1]
    ```

    The `↑1` means your local branch `gh-pages` is one commit ahead of
    the remote branch `gh-pages`.

    -   Select Team -> Push Branch 'gh-pages'.
    -   Leave everything as-is and select: Preview.
    -   Look over everything and click Push.
    -   You'll see another dialog confirming: "Pushed to <repository URL>".

    Your HTML/JS/CSS changes *should* show up in GitHub Pages!

7.  The process of merging everything into the `master` branch will be
    pretty much the same.
