# android-MakeJarWithAnt
This project demonstrate how to package .java files to .jar library with ant command line.

## Please follow the steps to build Calculator.jar
Calculator.jar package "src/calculator/Calculator.java" in this .jar file.

1. update android project to generate property files.
	```
	android update project -p C:\Users\Yeh\Desktop\AndroidJarMakerWithAnt --target android-23
	```

2. generate jar file.
	```
	ant jar
	```

3. check Calculator.jar in bin folder.

4. You can modify build.xml to include other .java files.
edit following block in build.xml:
	```
	<target name="jar" depends="release">
		<delete file="bin/Calculator.jar" />
	    <jar destfile="bin/Calculator.jar">
	      <fileset dir="bin/classes">
	        <include name="calculator/**" />
	      </fileset>
	    </jar>
	</target>
	```

