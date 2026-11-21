#命令行  参数  解析器
'''python
import argparse

parser = argparse.ArgumentParser(prog='XX')  #prog ->program  当 python todo.py(本地址) --help 时，终端上打印的提示信息开头就是XX，就是程序名

sub = parser.add_subparsers(dest='command', required=True)    #sub ->分支  required ->必要 
相当于要求了一个最开始需要接送的命令，这些命令接受在dest里边，当然具体命令也需要定义：


