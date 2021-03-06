jframe
======
A Common Plugin Framework implemented by Java. Without complex configuration, you can use it now.

## Why do I develop it
* I need a hot deployment system, which support remote update, daemon process, easy configuration, mainly for message processing and ensure that the message is not lost. 
* Osgi is too complex, fully dynamic characteristics is not what I needed most. 
* I think a framework composed by plug-in, the communication between the plug-in via the message is a good idea.
* So I decided to write a lightweight general framework based on dynamic plugins which communicate via the message.

## Quick Start
* `git clone git@github.com:dzh/jframe.git` On my pc, the repo is at ~/git/jframe
* `import jframe into eclipse`, then "Run as" -> "Maven install" to build on jframe project.
* `cd ~/git/jframe/jframe/jframe-release/jframe`, and then `ls temp`
<p>
if there are any *.pid files in temp folder,delete them first
</p>
* `bin/jframe.sh start`, maybe you need `chmod +x bin/*.sh`. (If a windows user, use startup.bat)
<p>
**Note**:
Before to  start, modify `vmargs` in config.properties.If running on linux, set `vmargs = ${app.home}/conf/vmargs`,
if on windows ,set `vmargs = ${app.home}/conf/vmargs-win`.
The default will start three plug-ins:jframe-example-pluin, jframe-swt and jframe-watch.
</p>
* `jps -l`, if output similar content, then jframe start successfully.
<pre>
13466 jframe.launcher.FrameMain
13451 jframe.launcher.Main
</pre>
You can also see log/*.log, or daemon.pid and app.pid generated in temp folder
* `bin/jframe.sh stop` (shutdown.bat), to stop jframe.

## About Jframe Manual
* Jframe's manual is jframe_manual_zh_CN.org in /jframe/doc/ directory.I edit it using Emacs's Org plug-in, and export a html version jframe_manual_zh_CN.html.
* Online address [jframe_manual_zh_CN](https://github.com/dzh/jframe/blob/master/doc/jframe_manual_zh_CN.org)

## Jframe Features
* v1.0.0
   * Run on jdk1.5 or higher
   * Use slf4j+logback as logging framework
   * Supoort daemon or normal launcher mode
   * Framework can be configured and can dynamically obtain configuration modification notification
   * Hot deployment plug-in system, and can control plug-in start/stop order
   * Communicate with each other via asynchronous message between plug-ins
* v1.1.0
  * Add plugin service feature, include annotations: `Service, InjectService, Start and Stop`
  * Add injecting feaure, include annotatiosn: `Injector, InjectPlugin, InjectService`. For example, `InjectPlugin` which injecting self-plugin instance into classes of the plugin
  * New options in the plugin.properties, `Plugin-Service, Import-Plugin, Import-class, Export-clazz`
  * New plugins
    * jframe-mybatis
    * jframe-datasource

## Question Contact
<pre>
jframe-dev@googlegroups.com  (u need join first)
archer.dzh@gmail.com         (personal)
</pre>


