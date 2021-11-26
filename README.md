# JAMstack Instagram API with Netlify
Tutorial: [Using the Instagram API + Serverless Netlify to display your own Photos in 2021](https://harrisonkolor.medium.com/using-the-instagram-api-serverless-netlify-to-display-your-own-photos-in-2021-7923014522d0)

## Facebook API
1. Created Facebook Developer account
2. Create an App. The article links to the Instagram Overview page but the [Getting Started tutorial](https://developers.facebook.com/docs/instagram-basic-display-api/getting-started) was most useful. This still took some searching to find the [Create App](https://developers.facebook.com/apps/create/) page.
    - Type: Consumer
    - Details: authenticated my FB account
3. Add Instagram Basic Display (clicked "Setup"). After that, things get confusing.
4. Add Instagram Tester (NOT a regular Tester).
5. Verify in Web Instagram Settings.
6. Generate User Token for the Tester account and save to `.env` file.
7. Find user id of Instagram account. Not sure why I need to send the token to get this?
    - From the tutorial: 
        - `https://graph.instagram.com/me?access_token={access_token}`
    - Also tried the URL from [this SO](https://stackoverflow.com/questions/11796349/instagram-how-to-get-my-user-id-from-username) but it didn't return anything that matched the above id.
8. Test the token and id:
    - `https://graph.instagram.com/{user-id}/media?fields=id, caption,link,media_url&access_token={access-token}`

## Netlify serverless functions
1. Create a new app for Netlify and copy/paste/update the code from the tutorial into `/netlify/functions/photos.js`.
    - install `axios` and `dotenv`
2. Authorized my Github Account on Netlify
3. Deployed from GH repo.
4. Build TOML configuration file
    - Traversy tutorial seems a little out of date? `netlify.toml`:
        ```
        [build]
          functions = "lamda"
        ```
    - 