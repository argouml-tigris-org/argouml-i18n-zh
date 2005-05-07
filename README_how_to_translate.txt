How to do a translating ??

1.First, you must be familiar with cvs, Ant
2.cvs checout files of this project , and files of main project ArgoUML
3.execute the target "reNewSource" of this project, which will update you 
  with the latest version of property files.
4.DO THE TRANSLATION. 
5.execute the target "patch_zh" of this project, which will patch property 
  file to src_new/org/argouml/i18n directory of main project.
6.execute the target "run" of main project, in Chinese system, you can see 
  the chinese automatically. Of course, in English system, you just see the
  english.
7. execute the target "clean" of this project, which will clean the zh 
   property file of main project, and the reNewSourced property file 


Jeff Liu 2005/05/07 21:30 (juain_farn@yahoo.com.tw)
