---
title: Fix NextJs 'prerendering page "/404"', 'error for page /_error', '<Html> shouhld not be imported outside of page/_document' Error
author: jaeman
date: 2025-12-25 04:23:00 +0900
categories:
tags:
toc: true
---
## The Error Occurred
```
@clinic/api:build: Error: <Html> should not be imported outside of pages/_document.
@clinic/api:build: Read more: https://nextjs.org/docs/messages/no-document-import-in-page

@clinic/api:build: Error occurred prerendering page "/404". Read more: https://nextjs.org/docs/messages/prerender-error

@clinic/api:build: Error: <Html> should not be imported outside of pages/_document.
@clinic/api:build: Read more: https://nextjs.org/docs/messages/no-document-import-in-page
```

error was occurred while running `next build`  (this is a bit strange it didn't occurred before)
I thought it was  because of patching 
- CVE-2025-66478
- CVE-2025-55184
- CVE-2025-55183
- CVE-2025-67779
But it was still happening when I `git reset` to previous version.  

I have tried to make `error.tsx`, `_error/404/page.tsx`, `not-found.tsx` but non of these were working.  
I could have found several solutions in nextjs discussion page
## Troubleshooting 1 - Check the NODE_ENV
In my case, `NODE_ENV` was setted in `.env` as  
```
NODE_ENV='development'
```
I have thought this should be 'development' in my local environment. but it was wrong.  
  
NextJs automatically threat `NODE_ENV` conditionally:  
```
npm run dev -> development
npm run build -> production
npm run start -> production
```

also I had to control `NODE_ENV` via `.env` filename, not the variable name  
`.env`, `.env.development`, `.env.production`

once I remove it from `.env`, it was solved.  
also nextjs is not recommend

## Troubleshooting 2 - run npm dedupe
`npm dedupe` scans your project and tell you if any packages is 'unresolvable' or 'vulnerabilities', or even the security issues with your version  

## Troubleshooting 3 - Downgrade react, react-dom from 19
I this should be the last resort. Downgrading react and react-dom version might cause more packages conflicts.  
But if you still face the errors, you can try this.