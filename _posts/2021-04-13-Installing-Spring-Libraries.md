Today I was trying out a Spring demo that ran on Eclipse. The demo was using Java modules, which are relatively new to me.
I found setting up the Spring libraries confusing, but it turns out, it's actually easy.

For a project with one module and one Spring configuration file, all you need to do is:
1. Download and install the Spring libraries.  Using the "dist" version of the binaries is apparently a fine choice.
    Put them any where you want, but remember where, as you will need that for the next step.
2. Add the libraries to the project.  The libraries should be added to the Modulepath, not the Classpath.
    Although the Spring libraries are not module libraries, we will be directly accessing them from our Java module code.
3. Make appropriate "requires" clauses for the Spring modules in your project's module-info.java file.
    The Spring module names are given [here](https://docs.spring.io/spring-framework/docs/3.0.0.M4/reference/html/ch01s02.html),
    but need to be made lowercase, and have "spring." prepended.  So, for example, the requires clause for the Spring "Context" module will <code>requires spring.context;</code>
4. Make "exports" clauses for any packages that contain beans you will want Spring to create.
5. Put any XML configuration file you use directly under the "src" directory.
    When eclipse builds your project, it will copy the configuration file to the top of the "bin" project directory, where Spring will look for it.
    (If you put your configuration file somewhere else under src, it will copy it to the corresponding spot under bin.)

Other difficulties:
- Putting my XML configuration file somewhere accessible.  Had to add its directory to my classpath.  I suspect that if my file structure included
    "src/main/resources", then I could have put it there without adding to the classpath?
