# Interactive Analytics with Shiny

We follow the same, consistent process to create and deploy a new Shiny app. Repeating these common tasks helps build skills and comfort with professional tools and processes. The instructions become more concise as we repeat things. For more detailed instructions, refer back to the earlier [SHINY.md](https://github.com/denisecase/cintel-02-app/blob/main/SHINY.md).

## Create a Virtual Environment

```shell
python -m venv .venv
```

## Activate the Virtual Environment

- Activate it on Windows: `.venv\Scripts\activate`
- Activate it on macOS/Linux `source .venv/bin/`

## Install Libraries into Virtual Environment

```shell
python -m pip install --upgrade pip wheel 
python -m pip install --upgrade black ruff pyright
python -m pip install --upgrade -r requirements.txt
```

🚀 Rocket Tip: When installing packages, spend a bit of time finding out what they are, where they go, and how you can use them to improve your work. 
Here's a short list of the [developer tools](https://github.com/denisecase/license-tracking/tree/main#open-source-python-developer-tools) and other [requirements](https://github.com/denisecase/license-tracking/tree/main#open-source-python-external-libraries). 

🚀 Rocket Tip: Format Python code automatically with Black. 
We've already installed [Black](https://pypi.org/project/black/) in our virtual environment.
Open a new Terminal window and run `black .` to format all files in the current folder.
That's black space dot. The single dot means the current folder.

## Run the App

Verify your virtual environment is activated. Run the app. 

```shell
shiny run --reload app.py
```

Open the app by following the instructions provided in the terminal. 
For example, CTRL click on the URL displayed (http://127.0.0.1:8000).

Hit CTRL c to quit the app. If it won't stop, close the terminal window.
Reopen the terminal window and be sure the virtual environment is activated
before running the app again.

## Deploy the App

We can copy the .github/workflows/deploy.yml from earlier. 
All we need to do is change the repository name in the last line
and configure the same 3 repository secrets as we did for our last repo. 
The keys and values are exactly the same. 
Login to [shinyapps.io](https://www.shinyapps.io/) to retrieve the values (you cannot retrieve them from GitHub). I log in via my GitHub account so I don't have to look up a password each time we do this. Go to Account / Tokens to find the values.

See the earlier [SHINYAPPS.md](https://github.com/denisecase/cintel-02-app/blob/main/SHINYAPPS.md) for details.

- Name: SHINYAPPS_ACCOUNT
- Secret: Paste or type your shinyapps.io account name.

- Name: SHINYAPPS_TOKEN
- Secret: (paste the token from shinyapps.io)

- Name: SHINYAPPS_SECRET
- Secret: (paste the secret from shinyapps.io)


-----

## ⚠️ Delete Hosted App Before Pushing to GitHub

Reminder: The GitHub action deploy.yml does not automatically delete an existing app from shinyapps.io so we can redeploy.

Before pushing to GitHub, login to [shinyapps.io](https://www.shinyapps.io/) and view the list of applications. 

- First archive the app.
- Then delete the archived app.

##  rsconnect deploy shiny . --name s566248 --title cintel-03-data
