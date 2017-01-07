# JAVA cheatsheet
------

## Maven Exec plugin
While using exec-maven-plugin to run `npm run build`, it works fine in Linux, but failed in Windows (Error: %1 is not a valid win32 program).
I made up some solutions to solve this problem, like designated the full path of the npm, read the plugins api etc.
Finally, I changed the `executable` parameter to `npm.cmd` and problem solved.

So that the pom file works fine in both Linux and Windows, I made a link file which named `npm` and point to `npm.cmd`.

### TODO
Consider to add some scripts or some steps instead of adding a link file manually. Like adding a link file automatically.

------

## JMeter cluster
-Djava.rmi.server.hostname=192.168.0.21



