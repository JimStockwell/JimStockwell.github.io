We all know how important it is to protect API keys, and that we shouldn't have them exposed in our code.
So where should they go?  One popular choice is to store keys in environment variables,
using some method other than loading the environment variables from the source code, and then accessing those variables at run time.

I am writing some AWS Lambda functions, and had a hard time finding a good way to set the environment variables.
Doing a google search, AWS documentation came up readily, and explained how to set environment variables for Lambda functions.
But, a careful reading (or trial and error) reveals that these methods are for setting environment variables for the *build* environment,
not the run-time environment.

The secret is: AWS Lambda run-time environment variables can be set from the Lambda console!
[This](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html) link shows how.
