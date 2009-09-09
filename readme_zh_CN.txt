如何进行ArgoUML的翻译工作？

==预备知识==
1、掌握Ant和SVN的基本用法
2、阅读ArgoUML的Developer wiki(http://argouml.tigris.org/wiki)，尤其是其中的国际化部分
3、相关的语言能力（这个是废话）
4、申请成为项目的观察员（Observer）并订阅邮件列表（至少必须订阅dev），否则项目内部交流将成为问题

==准备工作==
1、用SVN取回argouml-i18n-zh项目的所有文件
2、准备ArgoUML主程序，可以用SVN取回argouml项目，也可以直接下载argouml的发布版本的源代码，并放到
   argouml-i18n-zh项目的相邻目录中, 例如：argouml-zh-cn放在~/workspace/argouml-i18n-zh，则argouml
        就放在~/workspace/argouml-app

==build.xml的相关说明==
1、运行update_en_src，从argouml-app项目中取回所有的properties文件，这样就可以对它们进行翻译了。
	翻译后的文件应保存为**_zh_CN.properties和**_zh_TW.properties，并存放在
	argouml-i18n-zh/src/org/argouml/i18n/中。
2、运行patch_zh，将翻译好的**_zh_*.properties补充到argouml-app中。
3、运行run，即可运行argouml-app，如果已经选择了中文，这时就可以看到效果了。
	也可以直接运行patch_and_run，这个目标会自动执行patch_zh，接着再执行run。
4、完成工作后，运行clean，删除argouml-app中的**_zh_*.properties文件以及argouml-i18n-zh中从argouml
           中取回的英文properties文件。已经翻译好的文件不会被删除。用SVN client提交翻译好的**_zh_*.properties文件。

==辅助工具==
翻译时不能直接在文件中输入中文，必须转换为Unicode代码，这就使得翻译起来很不方便。
如果你正在使用Eclipse，你可以使用以下两个插件简化翻译工作：

	JInto：能够非常方便的编辑属性文件，支持多语种对照翻译。不过在翻译长字符串的时候不大方便。
		主页：http://www.guh-software.de/jinto_en.html
		Eclipse安装源：http://www.guh-software.de/eclipse/
		
	Properties Editor：使用这个就可以直接编辑属性文件了，打开和保存时会自动进行转换。
		主页：http://propedit.sourceforge.jp/index_en.html
		Eclipse安装源：http://propedit.sourceforge.jp/eclipse/updates/

-----------------------------------------
2006-09-11, Addone <addone@gmail.com> 创建
2009-09-09, Iridium <iridiumcao@gmail.com> 修订
