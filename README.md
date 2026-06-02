# GymLingo Legal Site

This folder is a static website for App Store Connect URLs:

- `https://gymlingo.app/`
- `https://gymlingo.app/privacy`
- `https://gymlingo.app/terms`
- `https://gymlingo.app/support`

## Deploy With Vercel

This repo includes a root `vercel.json` and `.vercelignore`, so deploying from the repository root serves this legal site without uploading Xcode build output.

From the repository root:

```sh
vercel --prod
```

The root `vercel.json` rewrites `/privacy`, `/terms`, and `/support` to the files in this folder. The root `.vercelignore` keeps Xcode build output, archives, and IPAs out of the deployment.

Then add `gymlingo.app` as a production domain in Vercel and point DNS at Vercel. After the domain is live, verify:

```sh
scripts/check_public_launch_urls.sh
```

The App Store metadata in `../appstore/metadata/en-US/` expects these URLs to be live before review submission.
