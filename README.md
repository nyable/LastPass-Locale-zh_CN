# LastPass-Locale-zh_CN
利用旧的本地化文件和机器翻译生成的LastPass简体中文语言文件。  
替换原来的语言文件，即可达到汉化效果。  

## 如何使用🚀

1.打开LastPass插件所在目录。通常命名为`C:\Users\你的用户名\AppData\Local\Google\Chrome\User Data\Default\Extensions\hdokiejnpimakedhajhdlcegeplioahd\`（Chrome version 87.0.4280.88）。可以试图在地址栏输入`%USERPROFILE%\AppData\Local\Google\Chrome\User Data\Default\Extensions\hdokiejnpimakedhajhdlcegeplioahd`或者搜索`hdokiejnpimakedhajhdlcegeplioahd`来打开该目录。  
2.目录中包括一个以版本号命名的文件夹，如：`4.65.0.3_0`。进入该文件夹，然后找到`_locales`文件夹，打开其中的`en_US`文件夹。  
3.下载github中的`messages.json`，替换/覆盖`en_US`文件夹中原有的文件。此处可以先对原文件进行备份，以便恢复英文版本。  
4.确保LastPass的语言选项是English。（默认已经是English）。  
5.关闭浏览器并重新打开。  
6.至此界面文本已经呈现简体中文。  

## 不同文件的差异🚥

  messages_old.json：仅提取了旧版本插件的汉化信息并进行替换，这个文件始终是最后一个拥有简中选项的插件的内容。  
  messages_include_word_in_1_4.json：在message_old.json的基础上，利用机器翻译批量翻译了单词量在1到4之间的文本，但是忽略掉了一些带有特殊符号的文本，可能会更新。  
  messages.json：在message_old.json的基础上,利用机器翻译批量翻译了大部分文本（排除了一些带有特殊功能符号的文本），并人工修正了一些翻译内容，可能会更新。  

## 简单的翻译迁移脚本
因为插件更新会导致汉化内容被还原，并且每次更新后对应的词条数量也在不断增加，而旧文件中是不会存在这些新词条的，可能导致一些文本显示很奇怪，比如首字母大小写格式，因此可以利用脚本将旧的汉化内容替换到新的文件中。这样能够在不影响新增内容显示的情况下，保留原有的翻译信息。   
### 替换步骤
1. 先在插件语言文件目录把最新的原版英文`messages.json`文件备份（直接复制粘贴也行）。
2. 用任意文本编辑器打开`script\old.js`，清空所有内容，然后输入`const o =`，复制旧的翻译文件的所有内容，直接粘贴到`=`号后面。
3. 用任意文本编辑器打开`script\new.js`，清空所有内容，然后输入`const n =`，复制`messages.json`(插件更新后的原版内容)的所有内容，直接粘贴到`=`号后面。
4. 用浏览器打开`index.html`，点击`替换并输出`按钮，输入区域显示的内容即为替换后的汉化内容，复制后覆盖`_locales\en_US`的`messages.json`即可。
5. `重启浏览器`或`停用再启用插件`后生效。
