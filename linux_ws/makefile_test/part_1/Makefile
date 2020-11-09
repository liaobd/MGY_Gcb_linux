#创建目标targeta，该目标依赖于targetb与targetc，该目标执行的命令是ls -lh
targeta:targetb targetc
	ls -lh
	
#创建目标targetb，该目标执行命令pwd
targetb:
	pwd
	
#创建目标targetc，该目标执行命令使用touch创建text.txt文件
targetc:
	touch text.txt
	
#创建目标targetd，该目标执行命令删除text.txt文件
targetd:
	rm -f text.txt
