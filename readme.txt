How to do translation:

==Prerequisite==
1. Knowing how to use Ant and SVN
2. Read the Developer wiki(http://argouml.tigris.org/wiki) of ArgoUML, especially the sections about localization (i18n)
3. The ability of reading and writing English and Chinese
4. Have been observer of this project, and have subscript the mailing lists (at least dev)

==Ready for work==
1. Retrieve argouml-i18n-zh project via SVN
2. Retrieve ArgoUML main project, either by SVN or by directly download. it needs to be put aside from argouml-i18n-zh.
	For example, if your argouml-i18n-zh at ~/workspace/argouml-i18n-zh, then you should put argouml at ~/workspace/argouml-app
	
==About build.xml==
1. Run the update_en_src target, that will retrieve all the properties file from argouml-app project(the main project), then you can translate them.
	The translated files should be saved as **_zh_CN.properties and **_zh_TW.properties into the argouml-i18n-zh/src/org/argouml/i18n/ folder.
2. Run the patch_zh target, that will patch the translated files into the argouml main project.
3. (some problem now)Run the run target, that will run argouml-app. If you have select Simplified/Traditional Chinese before, then you can see your work.
	Besides, you can run the patch_and_run target instead, that will perform the above 2 steps one after another.
4. Once you finish your work, run the clean target, and that will delete all patched files in argouml-app and all properties files retrieved from the main project.
	The translated files won't be deleted. You can commit your work via SVN.
	
==Tools==
When you edit the properties files, you cannot input chinese into them directly, instead, you must convert the chinese characters into unicode values.
It's annoying, but if you are using Eclipse, you can use the following plugins to save your time:

	JInto: A plugin for Eclipse that lets the developer easily edit and maintain resource bundles.
		 It supports contrast multiple language properties files. However, it is not so convenient when dealing with very long strings.
		 Website: http://www.guh-software.de/jinto_en.html
		 Eclipse install site: http://www.guh-software.de/eclipse/
		 
	Properties Editor: This editor can directly edit property files written in Unicode reference characters.
		Files can be opened in the IDE and saved in Unicode values automatically.
		Website: http://propedit.sourceforge.jp/index_en.html
		Eclipse install site: http://propedit.sourceforge.jp/eclipse/updates/
	
-----------------------------------------
2005-05-07 21:30, Jeff Liu <juain_farn@yahoo.com.tw>, Deleted
2006-09-11, Addone <addone@gmail.com>, Created
2009-09-13, Iridium <iridiumcao@gmail.com>, Edited
