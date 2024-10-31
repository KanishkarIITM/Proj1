- This project retrieves all GitHub users in Austin with over 100 followers and fetches their public repositories using the GitHub API.
- It was interesting to discover the diversity of programming languages and project types Austin developers work on.
- Based on the findings, developers can broaden their skill set by exploring popular languages in their area for better local networking and job opportunities.

## About This Project

The data in `users.csv` and `repositories.csv` provides an in-depth look at the GitHub users in Austin, Texas, with details on their profiles and their top repositories. This information can be helpful for market research, hiring, or discovering popular languages and technologies in a specific area.

## Files

- `users.csv`: Contains details of each GitHub user in Austin with over 100 followers.
- `repositories.csv`: Contains details of each user's repositories.
## Data Collection Process
This script uses the GitHub API to collect user and repository data for users located in Austin with more than 100 followers. Here’s a breakdown of how the data scraping process works:

## Search for Users:

The script searches for users by location and minimum follower count using GitHub's search/users endpoint.
With pagination, it collects all users in Austin with more than 100 followers, adjusting the page number in each request.
## Fetch User Details:

For each user found, the script calls the users/{username} endpoint to get additional details, such as name, email, and bio.
Company names are cleaned (e.g., trimmed whitespace, converted to uppercase, and any leading “@” symbol is removed).
## Retrieve Repositories:

The script retrieves up to 500 repositories per user by querying the users/{username}/repos endpoint, fetching details such as language, star count, and license.
Repositories are paginated to stay within GitHub’s API rate limits, with a one-second delay to ensure compliance.
## Save Data to CSV:

Collected user data is saved to users.csv with fields directly from the API, ensuring consistency in boolean values, nulls, and field names.
Repository data is saved to repositories.csv, also maintaining field accuracy for easier downstream analysis.
