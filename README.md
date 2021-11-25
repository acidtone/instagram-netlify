# JAMstack Instagram API with Netlify
Tutorial: [Using the Instagram API + Serverless Netlify to display your own Photos in 2021](https://harrisonkolor.medium.com/using-the-instagram-api-serverless-netlify-to-display-your-own-photos-in-2021-7923014522d0)

## Steps taken
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
    - From [this SO](https://stackoverflow.com/questions/11796349/instagram-how-to-get-my-user-id-from-username)
        - `https://www.instagram.com/{username}/?__a=1`
        - Which returns lots of info. Trying `graphql/user/fbid`