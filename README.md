making a PR

<h3 align="center">
<img src="https://raw.githubusercontent.com/codebam/cf-workers-telegram-bot/master/assets/logo.png" width="100" />
<br/>
CF workers telegram bot
<br/>
</h3>

<h6 align="center">
<a href="https://github.com/codebam/cf-workers-telegram-bot/wiki">Wiki</a>
 · 
<a  href="https://codebam.github.io/cf-workers-telegram-bot-docs/">Docs</a>
</h6>

<p  align="center">
<a href="https://github.com/codebam/cf-workers-telegram-bot/stargazers">  <img src="https://img.shields.io/github/stars/codebam/cf-workers-telegram-bot?style=for-the-badge&logo=starship&color=111111&logoColor=ffffff&labelColor=000000" alt="GitHub stars"/></a>
<a href="https://github.com/codebam/cf-workers-telegram-bot/issues">
  <img src="https://img.shields.io/github/issues/codebam/cf-workers-telegram-bot?style=for-the-badge&logo=gitbook&color=111111&logoColor=ffffff&labelColor=000000" alt="GitHub issues"/></a>
<a href="https://github.com/codebam/cf-workers-telegram-bot">  <img src="https://img.shields.io/github/forks/codebam/cf-workers-telegram-bot?style=for-the-badge&logo=git&color=111111&logoColor=ffffff&labelColor=000000" alt="GitHub forks"/></a>
<a href="https://www.npmjs.com/package/@codebam/cf-workers-telegram-bot">  <img src="https://img.shields.io/npm/v/@codebam/cf-workers-telegram-bot?style=for-the-badge&logo=npm&color=111111&logoColor=ffffff&labelColor=000000" alt="npm version" /></a>
</p>

![screenshot of cf-workers-telegram-bot](/screenshot.png)

```sh
npm i @codebam/cf-workers-telegram-bot
```

See `worker.ts` for an example of what a bot might look like. Just import from `@codebam/cf-workers-telegram-bot`.

- `npm create cloudflare@latest`
- `npx wrangler login`
- `npx wrangler secret put SECRET_TELEGRAM_API_TOKEN`, set it to your telegram bot token that you got from `@BotFather`
- `npx wrangler deploy`
- Open this url in your browser to set your webhook `https://your-worker.username.workers.dev/SECRET_TELEGRAM_API_TOKEN?command=set`

To set up GitHub actions to deploy when you push, see https://github.com/cloudflare/wrangler-action

---

These instructions are for if you want to deploy a copy of the bot along with
the library. Such as if you need extra API requests that haven't been
implemented yet.

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/codebam/cf-workers-telegram-bot)

- Click the deploy button
- Navigate to your new **GitHub repository &gt; Settings &gt; Secrets** and add the following secrets:

  ```yaml
  - Name: CLOUDFLARE_API_TOKEN  (should be added automatically)
  - Name: CLOUDFLARE_ACCOUNT_ID (should be added automatically)

  - Name: SECRET_TELEGRAM_API_TOKEN
  - Value: your-telegram-bot-token
  ```

- Push to `master` to trigger a deploy
