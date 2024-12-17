+++
title = 'Leetcode Submission Saver'
date = 2024-09-17T05:49:06+09:00
draft = false
+++

# Building the LeetCode Submission Saver Chrome Extension

As I progressed through my coding journey on LeetCode, I realized it was difficult to keep track of my progress and review the code I had written over time. This led me to start a project that would allow me to automatically commit successful LeetCode submissions to a GitHub repository, where I could easily look back at my code and track improvements.

## Objective

The primary objective of this project was to capture important information from my LeetCode submissions and make that data available in GitHub commits. The specific data I wanted to collect included:

- Submission data (i.e., the solution code)
- Question information (name, ID)
- Memory and speed performance metrics
- Programming language used

Once gathered, this data would be formatted and committed to a GitHub repository for easy tracking.

## Understanding the LeetCode API

The first challenge was identifying the necessary endpoints from LeetCode’s internal API. After digging into LeetCode’s API, I found two useful endpoints:

1. `/submit`: This endpoint handles the actual submission of the code.
2. `/check`: This endpoint checks the status of the submission, such as whether it’s pending, accepted, or failed.

These two endpoints were critical for collecting the data I needed for my project.

## Choosing GitHub Credentials: OAuth vs PAT

Next, I needed a way to authenticate the extension with GitHub so that it could automatically commit the data. Initially, I researched several ways to do this, including using GitHub OAuth and Personal Access Tokens (PAT).

While OAuth provides more robust security, it involves a more complex flow that requires managing tokens and callback URLs, which can be tricky in a Chrome extension environment. After weighing the options, I decided to use PAT for simplicity, even though it has limitations such as requiring the user to manually generate and input the token.

## Handling API Responses

One of the challenges I faced was accessing the **response body** of the `/submit` and `/check` API calls. It turns out that Chrome's `webRequest` API does not easily allow you to read the response body. To overcome this, I needed to **manually fetch** the data from the `/check` endpoint to retrieve the necessary submission status, memory usage, runtime, and other information.

## Mitigating Infinite Polling

The LeetCode API continuously polls the `/check` endpoint until the status of a submission changes from **PENDING** to something else, like **SUCCESS** or **FAILED**. I only cared about the **SUCCESS** status, which meant I needed a way to efficiently check for that status without endlessly polling the API.

My solution was simple but not perfect: after the initial `/submit` call, I introduced a **10-second delay** before fetching the `/check` API once to determine the status. This way, I mitigated infinite polling while ensuring I only cared about successful submissions.

## CSS and Switching to Tailwind

Once the functionality was in place, I started working on the design. Initially, I used plain CSS to style the popup interface, but I later decided to switch to **Tailwind CSS** for faster development. Unfortunately, using Tailwind’s CDN wasn’t possible due to Chrome’s **Content Security Policy** restrictions, so I had to set up Tailwind locally.

## Noteworthy Challenges

- **Chrome Security Restrictions**: Chrome extensions come with strict security guidelines, which made it difficult to use certain external resources (like CDNs). This pushed me to bundle Tailwind manually.
- **Handling PAT securely**: Storing the PAT locally using `chrome.storage.local` was straightforward, but it was important to remind users to use **minimal permissions** and **revoke** the token if needed.

## Conclusion

Building the **LeetCode Submission Saver** extension was a rewarding project. It allowed me to automate the process of tracking my LeetCode submissions and organize my solutions on GitHub. While there were challenges in handling APIs, choosing authentication methods, and managing Chrome's security restrictions, the project ultimately achieved its goal. The next steps could involve optimizing the polling mechanism and potentially improving the authentication flow using OAuth.

This project is a perfect example of how you can leverage simple tools like Chrome extensions, APIs, and GitHub to streamline and automate everyday tasks.
