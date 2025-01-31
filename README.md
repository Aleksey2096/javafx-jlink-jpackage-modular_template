# JavaFX modular template 

Includes jlink and shade plugins and resources for creating native windows installer using jpackage.

### Requirements

* Maven
* JDK 21
* WiX Toolset v3 (for creating native installer with jpackage)

## Project Setup

### 1. Clone or download the repository
```
$ git clone https://github.com/Aleksey2096/javafx-jlink-jpackage-modular_template.git
```

### 2. Run application
```
$ mvn clean javafx:run
```

### 3. Create executable fat .jar using maven-shade-plugin. Jar path = "target\hellofx-0.0.1-SNAPSHOT-shaded.jar"
```
$ mvn install
```

### 4. Move executable jar from "target\hellofx-0.0.1-SNAPSHOT-shaded.jar" to "jpackage\input\hellofx-0.0.1-SNAPSHOT-shaded.jar"

### 5. Create native installer file using jpackage and WiX Toolset
```
$ jpackage 
	-t exe 
	--name HelloFX 
	--app-version 1.0 
	--input jpackage/input 
	--main-jar hellofx-0.0.1-SNAPSHOT-shaded.jar 
	--dest jpackage/output_installer 
	--icon jpackage/icon/player.ico 
	--module-path jpackage/jmods 
	--add-modules javafx.controls,javafx.graphics,javafx.fxml,javafx.base 
	--win-shortcut
```

***

### 3+. Create custom runtime image (including .bat launcher) using javafx-maven-plugin. Launcher path = "target\hellofx\bin\launcher.bat"
```
$ mvn clean javafx:jlink
```
