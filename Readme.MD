>#PART-2

>### Prompt-One

# GitHub API automation code

A sample python application which demonstrates to create repositories within organization and upon 
creation repository it will automate protection of master branch using Branch Protection Rule.

[Repository creation and Branch Protection](https://github.com/niravhjoshi/GitHubHookWebApp)

## Scope of Project:-

>>For branches to be automatically protected upon creation.
> 
> >In this python application we have used simple arg parser to pass user's own argument like repository name and 
> they want to initialize repository with readme.md  and if they want to keep repository private.
> 
>>As part of this automation we have used extensively GitHub API for creation of 
> repository and then add branch protection rule on top of it.
> 
> >There is reference of token module in main.py file which i haven't included in this repo due to security reason.
> you can create new file "__secret.py__"  and add following code with GitHub PAT Token
> 
> >[GitHub PAT Token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token)
```
GITHUB_TOKEN = "MYTokenPAT of GitHUB"
```

```
from secret import GITHUB_TOKEN
```

>> In this python code when user will run this python code they need to give arguments at 
> runtime like name = "name of repository" and is_private if you want to keep private and auto_init if you wish 
> to initialize repository with Readme.MD file.
> 
> > In this case we must have to put __Readme.MD__ file because just empty repository will not have any branch and without 
> any branch we cannot enaable branchp rotection rule.
> 
> > Only change will be in HTTP Header of both API call 
>> 1. For POST to create Repository
> >2. For PUT to update created repository branch protection rule.
> 
 ```
headers = {
    "Authorization": "token " + GITHUB_TOKEN,
    "Accept":"application/vnd.github.v3+json"
}

putheaders ={
    "Authorization": "token " + GITHUB_TOKEN,
    "Accept":"application/vnd.github.luke-cage-preview+json"
}

```
> 
> 
> > In case of error requests library not found please install it using pip or pip3 python package manager.
> [Pip install](https://pypi.org/project/requests/)
> 
> > Please find screenshot for your reference to run project.
> ![Call Python Code using Command line](http://ultroniot.com/img/AutomationAPI.jpg)
> 
> 
> > In event of any exception you will be able to  view exact error message in command line from where you are running
> program.
 
>> __Reference Link__
>
> >[GitHub Create Repository API](https://docs.github.com/en/rest/reference/repos#create-an-organization-repository)
> 
> >[GitHub Update Branch Protection Rule API](https://docs.github.com/en/rest/reference/repos#update-branch-protection)