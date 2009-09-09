如何進行ArgoUML的翻譯工作？

==預備知識==
1、掌握Ant和SVN的基本用法
2、閱讀ArgoUML的Developer wiki(http://argouml.tigris.org/wiki)，尤其是其中的國際化部分
3、相關的語言能力（這個是廢話）
4、申請成為專案的觀察員（Observer）並訂閱郵件列表（至少必須訂閱dev），否則專案內部交流將成為問題

==准備工作==
1、用SVN取回argouml-i18n-zh專案的所有文件
2、准備ArgoUML主程序，可以用SVN取回argouml專案，也可以直接下載argouml的發布版本的源代碼，並放到
   argouml-i18n-zh專案的相鄰目錄中, 例如：argouml-zh-cn放在~/workspace/argouml-i18n-zh，則argouml
        就放在~/workspace/argouml-app

==build.xml的相關說明==
1、運行update_en_src，從argouml-app專案中取回所有的properties文件，這樣就可以對它們進行翻譯了。
	翻譯後的文件應保存為**_zh_CN.properties和**_zh_TW.properties，並存放在
	argouml-i18n-zh/src/org/argouml/i18n/中。
2、運行patch_zh，將翻譯好的**_zh_*.properties補充到argouml-app中。
3、運行run，即可運行argouml-app，如果已經選擇了中文，這時就可以看到效果了。
	也可以直接運行patch_and_run，這個目標會自動執行patch_zh，接著再執行run。
4、完成工作後，運行clean，刪除argouml-app中的**_zh_*.properties文件以及argouml-i18n-zh中從argouml
           中取回的英文properties文件。已經翻譯好的文件不會被刪除。用SVN client提交翻譯好的**_zh_*.properties文件。

==輔助工具==
翻譯時不能直接在文件中輸入中文，必須轉換為Unicode代碼，這就使得翻譯起來很不方便。
如果你正在使用Eclipse，你可以使用以下兩個插件簡化翻譯工作：

	JInto：能夠非常方便的編輯屬性文件，支持多語種對照翻譯。不過在翻譯長字符串的時候不大方便。
		主頁：http://www.guh-software.de/jinto_en.html
		Eclipse安裝源：http://www.guh-software.de/eclipse/
		
	Properties Editor：使用這個就可以直接編輯屬性文件了，打開和保存時會自動進行轉換。
		主頁：http://propedit.sourceforge.jp/index_en.html
		Eclipse安裝源：http://propedit.sourceforge.jp/eclipse/updates/

-----------------------------------------
2006-09-11, Addone <addone@gmail.com> 創建
2009-09-09, Iridium <iridiumcao@gmail.com> 修訂