

Packaging example:
<
jpackage 
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
>
