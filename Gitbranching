GIT branching strategy 
Distributed version control systems like Git give you flexibility in how you use version control to share and manage code. You can collaborate better and spend less time managing version control and more time developing code.The following branching strategies are based on the way we use Git here at Free-coding. 

 summarize this flow —

Our release flow encompasses the entire DevOps process from development to release. 

Branch
When a developer wants to fix a bug or implement a feature, they create a new branch off of our main integration branch. 

Push
When the developer is ready to get their changes integrated and ship their changes to the rest of the team, they push their local branch to a branch on the server, and open a pull request. Since we have several hundred developers working in our repository, each with many branches, we use a naming convention for branches on the server to help alleviate confusion and what we call branch proliferation. Generally, developers create a local branch named users/<username>/feature, where <username> is replaced with their account name.

Pull request
We use pull requests to control how  branches are merged into main. Pull requests ensure that branch policies are satisfied. For example, we build the proposed changes and run a quick test pass. Our first- and second-level test suites include around 60,000 tests that run in just under five minutes. This isn't our complete test matrix, but it's enough to quickly give us confidence in pull request.Next, we require that other members of the team review the code and approve the changes. 

Merge
Once all the build policies are satisfied and then the pull request is completed. This means that the branch is merged into the main integration branch, main.
After merge, we run additional acceptance tests that take more time to complete. These are more like traditional post-checkin tests and we use them to perform an even more thorough validation. pull request review while still having complete test coverage before release.


Keep your branch strategy simple:—

Build your strategy from these three concepts:
* Use feature branches for all new features and bug fixes.
* Merge feature branches into the main branch using pull requests.

Use feature branches for your work

Develop your features and fix bugs in feature branches based off your main branch. Feature branches isolate work in progress from the completed work in the main branch. Git branches are inexpensive to create and maintain. Even small fixes and changes should have their own feature branch.


￼

Ex—
 feature/FREEC-189
 bugfix/FREEC-189

Creating feature branches for all your changes makes reviewing history simple. Look at the commits made in the branch and look at the pull request that merged the branch.

Name your feature branches by convention:—
Use a consistent naming convention for your feature branches to identify the work done in the branch. You can also include other information in the branch name, such as who created the branch.

In Free-coding we do follow naming conventions:

* 		feature/FREEC-189

 Review and merge code with pull requests:—

The review that takes place in a pull request is critical for improving code quality. Only merge branches through pull requests that pass your review process. Avoid merging branches to the main branch without a pull request.

Reviews in pull requests take time to complete. may it will take time for FCS team they should agree on what's expected from pull request creators and reviewers. Distribute reviewer responsibilities to share ideas across FCS team and spread out knowledge of your codebase.

Some suggestions for successful pull requests:

* Two reviewers is an optimal number based on research
* Assigning to every pull requests people knows about the project (Revanth ). Pull requests work better when reviewer responsibilities are shared across the team.
* Include a build your changes running in a staged environment with your pull request. Others can easily test the changes.

up-to-date main branch

The code in your main branch should pass tests, build cleanly, and always be current. our main branch needs these qualities so that feature branches created by our team start from a good version of code.

Following on our main branches on policies :

* Requires a pull request to merge code. This approach prevents direct pushes to the main branch and ensures discussion of proposed changes.
* Automatically adds reviewers when a pull request is created. The added team members review the code and comment on the changes in the pull request.
* Requires a successful build to complete a pull request. Code merged into the main branch should build cleanly.

Manage releases

Use release branches to coordinate and stabilize changes in a release of our code. This branch is long-lived and isn't merged back into the main branch in a pull request, unlike the feature branches. Create as many release branches as you need. each active release branch represents another version of the code you need to support. Lock release branches when you're ready to stop supporting a particular release.

Use release branches

Create a release branch from the main branch when you get close to our release or other milestone, such as the end of a sprint. Give this branch a clear name associating it with the release, for example release/20.
Create branches to fix bugs from the release branch and merge them back into the release branch in a pull request.
￼

Port changes back to the main branch

Make sure that fixes in  both your release branch and our main branch. One approach is to make fixes in the release branch, then bring changes into your main branch to prevent regression in your code. 
In this topic, we'll cover making changes in the release branch and porting them into mainline. Use cherry-picking instead of merging so that you have exact control over which commits are ported back to the main branch. Merging the feature branch into the main branch can bring over release-specific changes you don't want in the main branch.
Update the main branch with a change made in the release branch with these steps:
1. Create a new feature branch off the main branch to port the changes.
2. Cherry-pick the changes from the release branch to your new feature branch.
3. Merge the feature branch back into the main branch in a second pull request.
￼
This release branch workflow keeps the pillars of the basic workflow intact: feature branches, pull requests, and a strong main branch that always has the latest version of the code.

Manage deployments
You can handle multiple deployments of your code in the same way you handle multiple releases. Create a clear naming convention, such as deploy/performance-test, and treat the environment branches like release branches. our team should agree on a process to update deployment branches with the code from your main branch. Cherry-pick bug fixes in the deployment branch back to the main branch. Use the same steps as porting changes from a release branch.

 


