
     關於Makefile，從以前第一次碰到時，就覺得這東西的語法很怪異，跟C和C++差很多。當時上網找教學文，發現都看不懂在寫什麼，不過經過幾年程式設計經驗後，最近看了一下教學，就莫名其妙的看懂一些了，所以發一篇自己消化後的教學文，來記錄一下。  
  
    附上參考的文章連結：  
    
    [Makefile簡易教學...][1]  
  
    [Makefile 語法簡介][2]  
  
####Makefile到底是什麼？  
    他不是.txt檔也不是.c或.cpp檔，大家一開始應該都會想要搞懂他的附檔名是什麼，老實說我現在也不知道，所以我都解讀成「就是某種Makefile的檔案類型」，應該也只是文件檔案，可以用vim開，也可以用Sublime Text開，所以就不太再去在意他的附檔名。  
  
    大學程式作業，助教應該都會要求或是提供一個Makefile，告訴你只要在command line輸入：  

	$ make
就應該會跑出一堆已經設定好的編譯指令，如果要刪掉就輸入：  

	$ make clean

最簡易的例子，假如某次code作業需要撰寫一份「hw1.c」，其中需要include一個「hw1.h」檔，並且編譯成「HW1」執行檔而不是「a.out」。而你Makefile內容應該會是：
	
	all: hw1.c hw1.h
	gcc hw1.c -o HW1
	clean:
	rm -rf HW1

接下來來解釋這幾行大概是什麼意思，
	
	all: hw1.c hw1.h
此行可以暫時解讀為，all後面是編譯需要的來源檔案，而下一行
	
	gcc hw1.c -o HW1

代表的是妳在command line輸入：  

	$ make

之後，即將會執行的指令。

而再來下面這段：  

	clean:
	rm -rf HW1

代表的是你執行：  

	$ make clean
	
的時候，會執行的指令。

所以最基本的就是這種功能。到此為止你應該已經可以寫出一次編譯好幾個執行檔的Makefile了，但是Makefile其實不只這些功能，改天有空再來補上更進階的Makefile心得。 

[1]: http://kevincrazy.pixnet.net/blog/post/29780477-makefile%E7%B0%A1%E6%98%93%E6%95%99%E5%AD%B8...
[2]: http://tetralet.luna.com.tw/?op=ViewArticle&articleId=185