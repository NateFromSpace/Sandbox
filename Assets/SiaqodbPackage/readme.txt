Siaqodb is a NoSql embedded object database engine for Unity3D. 
It can be used within all (basic/free and pro) Unity versions and for most popular platforms: 
PC, Mac, iOS and Android.

Features of Siaqodb for Unity3D:
-it is fully managed, written completely in C#
-only one assembly, no 3th party dependencies
-only two Mono dependencies: System.dll and System.Core.dll
-small footprint(siaqodb.dll has 240KB)
-it has very very simple API, LINQ is only query engine (not need to know SQL or other query language)
-your data is stored/retrieved in same way on Windows, Mac, iOS and Android, no code change for specific platform
-zero config
-persist your game data with one line of code: localDB.StoreObject(new Player(){Name="Player1",Score="100"});



To run SiaqodbDemo in Unity3D (min version 3.3.0f4) follow next steps:
--------------------
Windows and Mac:
--------------------
1.Select SiaqodbDemo\DemoRunner scene
2.Hit 'Play', the Game Simulator will run and result will be displayed to the Console.
3.If you want to run full examples, select SiaqodbDemo\ExampleRunner scene
4.Hit 'Play', the examples will run and result will be displayed to the Console.

--------------------
iOS:
--------------------
1.Go to \SiaqodbDemo\datalayer\DatabaseFactory and be sure you have set:siaoqodbPath =Application.dataPath; or a subfolder path
2.Select SiaqodbDemo\DemoRunner scene
3.Go to File->Build & Run-> press Build and Run -> it will create an X-Code project
4.Run X-Code project generated and open Debugger console, the Game Simulator will run and result will be displayed to the Console.
5.If you want to run full Examples, go to 3. and select ExamplesRunner scene and follow next steps
--------------------
Android:
--------------------
1.Go to \SiaqodbDemo\datalayer\DatabaseFactory and be sure you have set:siaoqodbPath=Application.persistentDataPath;
2.be sure you have installed Android SDK and from SDK Manager install at least "SDK Platform Android 2.2, API 8" but also "Android SDK Tools" and "Android SDK Platform-tools"
3.from Android SDK Manager go to Virtual devices and add a new Virtual Device that target at least Android 2.2 and the after creation press Start, to start Emulator
4.Select SiaqodbDemo\DemoRunner scene
5.from Unity3d project File-> Build&Run ->Build and Run:the project will start being deployed on Emulator
6.meanwhile go to Android SDK installed folder and start (usually from c:\Program Files (x86)\Android\android-sdk\tools\) the ddms.bat that will start Dalvik debugger
7.follow build process and see in debugger the result of Game Simulator run
8.If you want to run full Examples, go to 4. and select ExamplesRunner scene and follow next steps

!!!Important!!!
Persistent types must be defined in a separate assembly (see GameEntities project example), 
not directly in Unity3d project. Why? Because Unity3D build dynamically every time an assembly at every run for your C# classes/scripts and its name is different 
at every run and since Siaqodb store besides full namespace also assembly name where entities resides(to be able to re-build objects back), 
it is necessary that you have a separate assembly for your persistent entities.







