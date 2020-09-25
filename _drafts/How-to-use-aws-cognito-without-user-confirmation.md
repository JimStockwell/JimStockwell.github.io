Consider a scenario where you want to offer software as a service, with different users each having their own data,
but where you don't want to require people to provide or verify their email or phone number.  And you want to use AWS to manage the users.

You might consider going to
  "AWS Cognito Console,
  User Pools,
  General Settings,
  MFA and Verification,"
  and for "Which attributes do you want to verify?"
  selecting "No Verifications".
  But that won't work.
  [This GitHub issue](https://github.com/aws-amplify/amplify-js/issues/2906) talks about the problem but with no resolution.
  
It seems that the right route is not to tell Cognito anything particularly, but to use
  an AWS Lambda function as described [here](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-lambda-pre-sign-up.html)
  to auto-confirm users.
