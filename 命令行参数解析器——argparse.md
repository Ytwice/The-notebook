#命令行  参数  解析器
'''python
import argparse

parser = argparse.ArgumentParser(prog='XX')  #prog ->program  当 python todo.py(本地址) --help 时，终端上打印的提示信息开头就是XX，就是程序名

sub = parser.add_subparsers(dest='command', required=True)    #sub ->分支  required ->必要 
相当于要求了一个最开始需要接送的命令，这些命令接受在dest里边，当然具体命令也需要定义：

p_add = sub.add_parser("add")
也就是在*command*这个分支建立了一个叫**add**的小类（命令->command）
但是这个只是这个命令的名字，需要添加要*参数*：
p_add.add_argument("text",nargs="+")

*后续想要添加其他小类，也和上面一样。*

-以上是**将命令行参数解析器作为前端接受工具的所有前置定义**
以上操作：
 -将每个小类与其参数以类似于**类**的方式，打包：
 Namespace(command='add',text=['XXX'])



 作为前端的任务结束后，就到接受并运用相应数据的时候了：
 args = parser.parse_args()    #用args这个变量去接收数据
-args.command -> "add"|'其他'    
-args.text ->"接收的相应数据"    #.后的命名决定于你的定义



