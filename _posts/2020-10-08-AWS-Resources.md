## My Personal FAQ

- With Amplify and continuous deployment, how do `git push` and `amplify push` relate?
  - Tentative answer: It seems like you need to use both.
    `git` alone for code changes, both `git` and `amplify` for AWS configuration changes.
    When doing a configuration change that requires `amplify`, use `amplify push` first, then `git push`.
- With Amplify CLI, in what order should categories be added?
  - Add Function category resources after resources that you might want them to access,
    so that the functions can be automatically granted access to chosen resources.
  - Add Api after the functions it calls are created, or if creating them as part of creating the Api, see above.
  - Add Hosting very last.  After a minimially viable deployment is ready in github, if you plan to use continuous deployment.
- When choosing a "friendly name" for a resource in Amplify CLI, be aware, the name is global to the account, not just local to a CloudFormation stack.
- The [Amplify Libraries](https://docs.amplify.aws/lib/q/platform/js) for JavaScript make front-end interactions with AWS a lot easier.

