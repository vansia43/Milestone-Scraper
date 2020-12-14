# Milestone-Scraper
# Overview
If you want to download data from a GitHub repository's milestone, you can use this Jupyter Notebook to create a list of issues and PRs that are associated with the milestone. The Milestone Scraper parses raw HTML to create a list of issues and PRs by title, link, and ID. This information can be helpful when developing reports or release notes, outside of GitHub.
# Prerequisites
Before using the Milestone Scraper, ensure that you have the following prerequisites downloaded and installed:
- Python 3
- Jupyter Notebook
- ChromeDriver - If you do not have Chrome browser, you can use another browser's driver.

# Using the Milestone Scraper
## Step 1: 
Open the [template.ipynb](template.ipynb) file. 
## Step 2:
Update the `URL` variable with the URL for the milestone page. Note that you will need to run the notebook twice if you want a list of open and closed issues/PRs. 
## Step 3:
Run all commands at the same time.

The output is generated at the bottom of the notebook in the following format: 
~~~~
Issue or PR Title
https://github.com/samplerepo/pull/123
123
~~~~
Issues and PRs that are associated with the milestone are treated the same way in the output. You can copy and paste the output for use in another program.

# Additional Information
The Milestone Scraper uses Selenium to automate launching a browser. The `headless` option is set to `true`, which prevents the browser from actually launching. As a result, all work is completed in the background. A `wait` option is set to `10` seconds. Without this option, the JavaScript does not load fast enough for Selenium to pick up the data. The scraper gets the page source. Then, the page source is parsed using [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup). Beautiful Soup is a Python library that works along with a parser to pull data from HTML and XML libraries. Beautiful Soup finds all of the HTML sections for the milestone page. The module iterates over each element to get the title, link, and ID. The output is displayed for use in other contexts.
