# android-MakeJarWithAnt
This project demonstrate how to package .java files to .jar library with ant command line.

## Please follow the steps to build Calculator.jar
Calculator.jar package "src/calculator/Calculator.java" in this .jar file.

1. set environment path
	1. set jdk path. e.g.: JAVA_HOME=C:\Program Files\Java\jdk1.7.0_79
	2. set sdk path. e.g.: ANDROID_HOME=C:\Android\android-sdk
	3. add following paths to environment path.
		1. %JAVA_HOME%\bin
		2. %ANDROID_HOME%\platform-tools
		3. %ANDROID_HOME%\tools
2. update android project to generate property files.
	```
	android update project -p %absolute_path_for_this_project% --target %android_platform%
	```
	For example:
	```
	android update project -p C:\Users\Yeh\Desktop\AndroidJarMakerWithAnt --target android-23
	```

3. generate jar file.
	```
	ant jar
	```

4. check Calculator.jar in bin folder.

5. You can modify build.xml to include other .java files.
edit following block in build.xml:
	```xml
	<target name="jar" depends="release">
		<delete file="bin/Calculator.jar" />
	    <jar destfile="bin/Calculator.jar">
	      <fileset dir="bin/classes">
	        <include name="calculator/**" />
	      </fileset>
	    </jar>
	</target>
	```
