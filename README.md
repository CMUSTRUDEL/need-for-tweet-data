This dataset contains 70,427 cross-linked Twitter-[GHTorrent](http://ghtorrent.org) user pairs identified as likely belonging to the same users. The dataset accompanies our research paper:

```
@inproceedings{fang2020tweet,
  author = {Fang, Hongbo and Klug, Daniel and Lamba, Hemank and Herbsleb, James and Vasilescu, Bogdan},
  title = {Need for Tweet: How Open Source Developers Talk About Their GitHub Work on Twitter},
  booktitle = {International Conference on Mining Software Repositories (MSR)},
  year = {2020},
  pages = {to appear},
  publisher = {ACM},
}
```
 
The data **cannot** be used for any purpose other than conducting research. 

Due to privacy concerns, we only release the user IDs in Twitter and GHTorrent, respectively. We expect that users of this dataset will be able to collect other data using the Twitter API and GHTorrent, as needed. Please see below for an example.

To query the Twitter API for a given user_id, you can:

- Apply for Twitter developer account [here](https://developer.twitter.com/en/apply-for-access)  
- Create an APP with your Twitter developer account, and create an "API key" and "API secret key".
- Obtain an access token. Given the previous API keys, run: 

  `curl -u "<API key>:<API secret key>" --data "grant_type=client_credentials" "https://api.twitter.com/oauth2/token"`

  The response looks like this: `{"token_type":"bearer","access_token":"<...>"}`

  Copy the "access_token".

- Given the previous access token, run:

  `curl --request GET --url "https://api.twitter.com/1.1/users/show.json?user_id=<user_id>" --header "authorization: Bearer <access_token>"`

The GHTorrent user ids map to the users table in the MySQL version of GHTorrent. To use GHTorrent, please follow instructions on the [GHTorrent website](https://ghtorrent.org).
