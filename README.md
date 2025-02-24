# NextAuth Session Null in getServerSideProps - Next.js 15

This repository demonstrates a bug where the session object returned by `unstable_getServerSession` in `getServerSideProps` is always null, even when the user is logged in. This occurs in Next.js 15.

## Bug Description

The `getServerSideProps` function in `pages/about.js` attempts to retrieve the user session using `unstable_getServerSession`. However, the `session` object consistently returns null, regardless of whether the user is logged in or not.

## Reproduction Steps

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Observe that the "Please sign in" message is always displayed, even after successful login.

## Solution

The solution involves using `getServerSideProps` correctly in conjunction with NextAuth's `getSession` method.