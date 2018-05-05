增强Eclipse自动提示功能
=====================================
Eclipse中默认是输入"."后出现自动提示，用于类成员的自动提示，可是有时候我们希望它能在我们输入类的首字母后就出现自动提示，可以节省大量的输入时间（虽然按快捷键也会出现提示，但还是要多按一次按键，太麻烦了）。

    从Window -> preferences -> Java -> Editor -> Content assist -> Auto-Activation下，我们可以在"."号后面加入我们需要自动提示的首字幕，比如"ahiz"。

    然后我们回到Eclipse的开发环境，输入"a"，提示就出现了。

但是我们可以发现，这个Auto-Activation下的输入框里最多只能输入5个字母，也许是Eclipse的开发人员担心我们输入的太多会影响性能，但计算机的性能不用白不用，所以我们要打破这个限制。

在"."后面随便输入几个字符，比如"abij"，然后回到开发环境，File -> export -> general -> preferences -> 选一个地方保存你的首选项，比如C:/a.epf

用任何文本编辑器打开a.epf，查找字符串“abij”，找到以后，替换成 “abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ_. ”，总之就是你想怎样就怎样！！然后回到Eclipse，File -> import -> general -> preferences -> 导入刚才的a.epf文件。此时你会发现输入任何字母都可以得到自动提示了。

最后：自动提示弹出的时间最好改成100毫秒以下，这样会比较爽一点，不然你都完事了，自动提示才弹出来:)，不过也要看机器性能。
======================================================
这样修改后提示快多了.但是Eclipse那恼人的上屏键太恶心了..连空格都是上屏..甚至字母本身也能上屏..这里就要修改的更人性化一点.只用TAB和回车上屏(大部分人的习惯).
======================================================

 


解决候选列表上屏键修改(用TAB和回车上屏,可自改)
首先，打开Eclipse，打开window->show view，选择Plug-ins，再找到org.eclipse.jface.text，右键单击，选择import as－> Source Project，导入完成后，在你的workspace就可以看到这个project了。
在导入工程下的“org.eclipse.jface.text.contentassist.CompletionProposalPopup#verifyKey()”函数中有一段代码

if (contains(triggers, key)) {

...

将这段代码改为

if (key!=0x20 && key!='=' && key!=';' && contains(triggers, key)) {

...

还有把这段代码之上的代码注释掉
case '/t':
e.doit= false;
fProposalShell.setFocus();
return false;
修改为
case '/t':
e.doit= false;
insertSelectedProposalWithMask(e.stateMask);
break;

经过上述操作，这个辅助输入插件已经排除了空格与“=”的选中功能，增加了TAB键的选中功能。

最后就是导出修改后的插件，右键点击你的workspace里的工程，选择Export－>Deployable plugins and fragments，点击Next，选择Destination选项卡，选择Directory，选择一个要保存插件的目录，然后Finish。然后就会 在你所选的目录下产生一个新的plugins目录，里面有一个jar文件，用它替换掉eclipse/plugins里面的 org.eclipse.jface.text_3.6.1.r361_v20100825-0800.jar(这个文件不同版本的Eclipse，后面 的版本号会不一样，我用的Eclipse 3.6)，这样就大功告成了！