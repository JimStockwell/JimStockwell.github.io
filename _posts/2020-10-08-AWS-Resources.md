## My Personal FAQ

- With Amplify and continuous deployment, how do `git push` and `amplify push` relate?
  - Tentative answer: It seems like you need to use both.
    `git` alone for code changes, both `git` and `amplify` for AWS configuration changes.
    When doing a configuration change that requires `amplify`, use `amplify push` first, then `git push`.

    
