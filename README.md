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
          nl2br
          htmllentities();
          htmlspecialchars
          stripslashes() 
          strip_tags()
 
 *	其它的字符串格式化函数
  
            number_format()
            strrev()
            md5();
            md5_file();
 
 *	在PHP中所有字符串处理函数，都不是在原字符串上修改， 而是返回一个新格式化后的字符串。
 
        admin 

         字符串比较函数 ==  <

         strcmp($str1, $str2)
         strcasecmp()

          $str1 == $str2    0
          $str1  >  $str2   1
          $str1 < $str2     -1
      
 
 *	以上是按字节顺序， 以下是按自然数排序
 
         strnatcmp()









