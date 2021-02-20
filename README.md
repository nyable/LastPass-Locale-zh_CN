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

  messages_old.json：仅提取了旧版本插件的汉化信息并进行替换。  
  messages_include_word_in_1_4.json：在message_old.json的基础上，利用机器翻译批量翻译了单词量在1到4之间的文本，但是忽略掉了一些带有特殊符号的文本。  
  messages.json：在message_old.json的基础上,利用机器翻译批量翻译了大部分文本（排除了一些带有特殊功能符号的文本），并人工修正了一些翻译内容。  
