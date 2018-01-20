# php-string
php-常用的内置字符串处理函数


 * 字符串的特点
 
          substr("string", 2, 4);
          substr(123456789, 2, 4);
 	
 	1. 其它类型的数据用在字符串处理函数中，会自动将其转为字符串后，再处理
 	2. 可以将字符串视为数组，当做字符集合来看待
  

              $str="abcdefg";
              echo $str[2];
              echo $str{2}; 
 
    
   强大的PHP中内置字符串处理函数
   
   1. 常用的字符串输出函数
 
          echo()
          print()
          die() --- exit();
          printf()  格式化字符串
          sprintf() 返回格式化的字符串(	%%	%b	%c	%d %f %o %x %s)
      
  2. 常用的字符串格式化函数
  
  
  
                strlen()  获取字符串长度
                ltrim()   函数移除字符串左侧的空白字符或其他预定义字符 
                rtrim()   移除字符串右侧的空白字符或其他预定义字符
                trim()    移除字符串两侧的空白字符或其他预定义字符
              
              
              ltrim(string,charlist)

                     string 必需。规定要检查的字符串。

                     charlist
                     可选。规定从字符串中删除哪些字符。如果省略该参数，则移除下列所有字符：
                     "\0" - NULL
                     "\t" - 制表符
                     "\n" - 换行
                     "\x0B" - 垂直制表符
                     "\r" - 回车
                     " " - 空格
                    	$str = "        Hello World!";
                          echo strlen($str);     //20
                          echo "<br>";
                          echo  strlen(ltrim($str));  //12
                          
                          

                       $str = "$   Hello World!";
                         echo $str;      输出  $ Hello World!
                         echo "<br>";
                         echo  ltrim($str,"$");    输出   Hello World! 
                    
                    
      
 * 指定字符串长度不够在补充 
 
    	   str_pad()
        
            $str="linyuxun";
           echo str_pad($str,10,"o");  //输出 linyuxunoo   这里指定10个长度，不够补充后面o添加上
           echo str_pad($str,10,"pp",STR_PAD_BOTH)  输出plinyuxunp  不够10个长度   两边开始补充
           echo str_pad($str,10,"ll",STR_PAD_LEFT); 输出 lllinyuxun     不够10个从左边开始补充
 
*大小写有关的函数
  
          strtolower();  将字符串转化为小写
          strtoupper();  将字符串转化为大写
          ucfirst();    将字符串的首字母转换为大写
           ucwords — 将字符串中每个单词的首字母转换为大写
           
          和HTML标签相关的字符串格式化
           
          nl2br    在字符串所有新行之前插入 HTML 换行标记
          
             $str="abc
             def
             www
             hello
             aaaa
             bbb
            ";

         echo $str."<br>"; abc def www hello aaaa bbb 
         
         echo nl2br($str);
                   abc<br />
                   def<br />
                   www<br />
                   hello<br />
                   aaaa<br />
                   bbb<br />
          htmllentities();  把HTML 实体转换为内容：
          
          htmlspecialchars   去掉实体(用户输入什么内容就输出什么内容)  推荐用这个

          stripslashes() 去掉 \ 
          
              $str = "Is your name O\'reilly?";
               echo stripslashes($str); 输出: Is your name O'reilly?
                 一般我们都是这样配套使用   echo htmlspecialchars(stripslashes($_GET["str"]))."<br>";

            strip_tags()  删除用户输入的html标签
           
 
 *	其它的字符串格式化函数
  
            number_format()   以千位分隔符方式格式化一个数字
            
                	$price=123456789.123;

			echo $price."<br>";       123456789.123
			echo number_format($price)."<br>";    123,456,789
			echo number_format($price, 2)."<br>";  123,456,789.12
			echo number_format($price, 2, ',', '.')."<br>";  123.456.789,12
			echo number_format($price, 2, '.', ',')."<br>";  123,456,789.12
                
             
              strrev()   反转字符串
              md5(); 数字加密 (一般用于密码加密)
              
              	  $pass="1234&#abc";
	              echo md5($pass);      输出 3f816eb766b44d688b9dfe81961260fc
               
                  md5_file();对整个文件加密
 
 *	 在PHP中所有字符串处理函数，都不是在原字符串上修改， 而是返回一个新格式化后的字符串。


         字符串比较函数 ==  <
             strcmp($str1, $str2)   区分大小写
             strcasecmp($str1, $str2) 不区分大小写
      
	       $str1 == $str2    0
	       $str1  >  $str2   1
	       $str1 < $str2     -1
 
	以上是按字节顺序， 以下是按自然数排序
 
            strnatcmp()



   字符串处理函数 
   
			  strstr():(不区分字符串大小写) — 查找字符串的首次出现  
			  stristr():(区分字符串大小写)  功能一样

                            例子 ；
			     echo stristr("this is a test hrello", "test");  输出：test hrello
                             echo strstr("this is a tedst", 100);   输出   dst
			     
			     
                             strpos() :(不区分字符串大小写) 查找字符串首次出现的位置
			     strrpos() :(区分字符串大小写) 
				$mystring = 'bca';
				$findme   = 'a';
				echo strpos($mystring, $findme); 输出 2

