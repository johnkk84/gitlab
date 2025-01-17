# Create your first project, Sample execution, Why it not works?

## Description
We will configure our SCM (Source Code Manager) using git and will send small piece of
project into Gitlab repository. Exercise assumption is to fix AutoDevops.

### Before we start.
First of all personal token should be generated and assigned to gitlab user.

When you will log to github click as on above picture is:

Settings:

![](./images/create-gitlab-token.jpg "")

Next click, Access Tokens and fill up form similar to below screen:

![](./images/create-token-form.jpg "")

Be aware save your token in safe place (KeyPass)
![](./images/save-token-in-keypass.jpg "")

### Configure git to push code into Gitlab SCM:
We must initialize git to push our code into repo:

Plese enter into projects/my-first-project and execute below commands:

```
$ git init .
Initialized empty Git repository in /home/plp12439/Code/Education/gitlab/projects/my-first-project/.git/
$ git checkout -b master
Switched to a new branch 'master'
$ git branch
$ git remote add my-first-project https://gitlab:gdusoNkZVJRBo3fZEryU@cicd/gitlab/my-first-project.git
$ git remote -v
my-first-project	https://gitlab:gdusoNkZVJRBo3fZEryU@cicd/gitlab/my-first-project.git (fetch)
my-first-project	https://gitlab:gdusoNkZVJRBo3fZEryU@cicd/gitlab/my-first-project.git (push)
$ git add -A .
$ git commit -m "My first commit in my first project"
[master (root-commit) 88aa104] My first commit in my first project
.
..
...
To https://gitlab:gdusoNkZVJRBo3fZEryU@cicd/gitlab/my-first-project.git
 * [new branch]      master -> master
```

Check if your code is inside Gitlab SCM:

![](./images/my-first-project-repo-synch.jpg "")

### Enable AutoDevops

If you would like to start your pipeline automatically you need to enable AutoDevops mechanism. We will use Continous Deployment (human less).

![](./images/auto-devops-enable-1.jpg "")

Fill form as is on screenshoot and click save:
![](./images/auto-devops-enable-2.jpg "")

It is still in stuck mode. Why? Because we are using different gitlab pipeline definition file. We need adjust this in project configuration.

![](./images/auto-devops-custom-pipeline-file.jpg "")

Remember to click "Save changes"

![](./images/save-changes-pipeline-config.jpg "")

When it will be change Gitlab should trigger auto build project and go through .gitlab-ci-p1.yml. Please stop for the moment and study pipeline definition.


You should have similar output:

![](./images/run-pipeline-01.jpg "")
![](./images/run-pipeline-02.jpg "")
