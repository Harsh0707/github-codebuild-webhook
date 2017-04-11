Github CodeBuild Webhook
------------------------

This project will setup an api gateway endpoint, which you can have your github repository connect to. This will start and update a commit with the current build status.
This will be triggered for any PR update, on any branch.

Installation
------------
1. Create a github api token here: https://github.com/settings/tokens/new
2. Add the github token to your ENV vars: `export GITHUB_KEY=xyz`
3. Add your github username to your ENV vars: `export GITHUB_USERNAME=foobar`
4. Add your AWS CodeBuild project name to your ENV vars: `export BUILD_PROJECT=my-build-project`
5. Deploy the application with Serverless: `sls deploy`
6. Note the endpoint for the trigger, eg: `https://[id].execute-api.eu-west-1.amazonaws.com/dev/trigger`
7. Add that endpoint as a webhook on your repository: https://github.com/[username]/[repo-name]/settings/hooks/new
   Be sure to to select `Let me select individual events.` and then `Pull request`, so it's only triggered on PR updates.
8. Create a PR, and see the magic be invoked :)


Examples
--------
![Build pending](https://www.dropbox.com/s/ymyogjmy0w8oyyk/Screenshot%202017-04-11%2014.16.17.png?dl=1)
![Build succeeded](https://www.dropbox.com/s/7h2verouqexan5o/Screenshot%202017-04-11%2014.16.53.png?dl=1)
