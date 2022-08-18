### Introduction
The project was forked from [this guy](https://github.com/cmlanche/uiautomatorviewer-standalone), the guy didn't adapt to ubuntu, so I pulled it down and changed it

My system version is **Ubuntu 18.04.5 LTS** If there are problems with other versions, you can adapt them yourself

This project is [Google's official UIAutomatorViewer](https://android.googlesource.com/platform/tools/swt/+/refs/heads/android10-release/uiautomatorviewer/), a tool used to grab UIAutomator controls , supports independent operation, but because it depends on swt, it needs to be compiled separately under mac and windows.

### Release address
[Download](https://github.com/lyp82nlf/uiautomatorviewer-standalone-ubuntu/releases/tag/1.1)

### Build applicaton
mvn clean package

### start up
Under mac:
```shell
java -XstartOnFirstThread -jar uiautomatorviewer-standalone-1.0-SNAPSHOT-all.jar
````
Under windows:
```shell
java -jar uiautomatorviewer-standalone-1.0-SNAPSHOT-all.jar
````
Under ubuntu:
```shell
java -jar uiautomatorviewer-standalone-1.0-SNAPSHOT-all.jar
````

If adb cannot be used, soft link your own adb to the current directory
```shell
ln -s /<SDK_DIR>/platform-tools/adb ./adb
````

### Source code
The source code comes from [Google official](https://android.googlesource.com/platform/tools/swt/+/refs/heads/android10-release/uiautomatorviewer/)

After checking the dependencies, find the relevant libraries (the links below are basically invalid):
1. swt: https://download.eclipse.org/eclipse/downloads/drops4/I20200830-1800/#SWT
2. jface: Download [RCP Runtime Binary](https://download.eclipse.org/eclipse/downloads/drops4/I20200830-1800/), unzip it and find org.eclipse.core.commands_{version}.jar, org .eclipse.equinox.common_{version}.jar, org.eclipse.jface_{version}.jar
3. Additional dependencies are included:
````xml
<dependency>
    <groupId>commons-io</groupId>
    <artifactId>commons-io</artifactId>
    <version>2.7</version>
</dependency>
````

### Preview
![UIAutomatorViewer](https://indiehackers-1251406926.cos.ap-chengdu.myqcloud.com/hackers/3d1o1.png)
