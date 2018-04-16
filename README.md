
使用Notepad++运行xelatex文件：

1， 安装参考
https://blog.csdn.net/sunbibei/article/details/51443499

2， 上述版本仅仅可以供pdflatex使用，或者使用下面的语法。  
Old version for pdflatex:    
```
  NPP_SAVE                           //save the current file;  
  cd $(CURRENT_DIRECTORY)   
  pdflatex.exe  $(NAME_PART).tex     //run the padlatex program;  
  gbk2uni.exe $(NAME_PART).out        //编译.out文件  
  pdflatex.exe  $(NAME_PART).tex      //再编译一次，避免生成的书签乱码  
  NPP_RUN $(NAME_PART).pdf           //show the resulting LaTeX created PDF;  
```

3，但是有不少中文去编辑tex，需要大家去使用xelatex，那么如何去用notepad++执行呢？大家可以修改Plugins -> NppExec -> Execute，改成以下语法：    
new version for xelatex:     
```
  NPP_SAVE                           //save the current file;  
  cd $(CURRENT_DIRECTORY)   
  xelatex.exe  $(NAME_PART).tex       //run the padlatex program;  
  makeindex $(NAME_PART).idx  
  bibtex $(NAME_PART).bib  
  gbk2uni.exe $(NAME_PART).out        //编译.out文件  
  xelatex.exe  $(NAME_PART).tex       //再编译一次，避免生成的书签乱码  
  NPP_RUN $(NAME_PART).pdf           //show the resulting LaTeX created PDF;  
```

