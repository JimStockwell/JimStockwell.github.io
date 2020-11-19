Bruno Leite posted an interesting tutorial,
["Build a Spring Boot Application Using Java Modules"](https://developer.okta.com/blog/2020/07/27/spring-boot-using-java-modules#create-the-persistence-module).
Following are some of the lessons I took from it.

## Directory Structure Can Be Reasonable

I don't like long names unless they convey important information.
The module examples I'd seen and read about
involved long reverse domain name format module names
fully reflected in the project directory tree,
followed by long reverse domain name format package names.
Ouch!

So, I was delighted to discover that using long module name
as part of the project directory tree is unnecessary.
Well, it is necessary, **if** your project is composed in "Multi-Module Mode"
(see [JEP 261](http://openjdk.java.net/jeps/261)), but that is not the only choice.

[Bruno's tutorial](https://developer.okta.com/blog/2020/07/27/spring-boot-using-java-modules#create-the-persistence-module)
illustrates using the "Single-Module Mode",
in which you can name your Java module directories anything you want.

## POM Files

Before
[Bruno's tutorial](https://developer.okta.com/blog/2020/07/27/spring-boot-using-java-modules#create-the-persistence-module),
I had never explicitly used a multi-level POM file.

Now, compiling in Single-Module Mode,
and giving each module its own POM file,
tying them all together with a higher level POM makes nice sense.
And it's clean and easy.

Speaking of POM files, it may be tempting to think of "module" tags
and "parent" tags as complimentary links that do not carry separate information.
But, that's not the case.
The parent tags indicate where to inherit default settings from.
The module tags indicate where to find sub-POM files.
They still sound almost opposite, but you can have either without the other.
(They are quite the opposite of Frank Sinatra's conclusion in "Love and Marriage".)

## Conclusion

While implementing Java Multi-Module programs, you can still have a simple directory structure, and a simple POM structure.
Enjoy!
