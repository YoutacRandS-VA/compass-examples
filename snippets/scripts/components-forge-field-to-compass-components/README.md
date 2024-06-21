Use this script to copy values in your issues' Compass custom field to their Components field. This is so you can use the new Compass components integration with your company-managed Jira Software projects.

## Before you begin
Make sure the projects you want to affect are switched to Compass components. Learn how: https://support.atlassian.com/jira-software-cloud/docs/switch-between-jira-and-compass-components/
In addition, we need you prepare the API token for your Atlassian account. Learn how:  https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/

## Local environment setup
Install Python3
```shell
brew install python3
```
Install PIP3 command
```shell
python3 -m pip install --upgrade pip
```

Ensure you have a working python and pip:
```
python3 --version
python3 -m pip --version
```

Install requests module
```shell
pip3 install -r requirements.txt
```

## How to run locally
First run file jiraProjectsInfo.py to collect your site's projects info. 
```shell
python3 ./jiraProjectsInfo.py
```

Please save the projects' keys. You can save keys by manually copying script output or redirecting the output to a file:
```shell
python3 ./jiraProjectsInfo.py > project_keys.txt
```

or copying the output to clipboard:
```shell
python3 ./jiraProjectsInfo.py | pbcopy
```

Second run file `migrateCompassCFToComponent.py` to migrate CompassCF to component field in all related issues in the project you want.
```shell
python3 ./migrateCompassCFToComponent.py
```

## Other Useful Links
- https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-projects/#api-group-projects
- https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-issues/#api-group-issues