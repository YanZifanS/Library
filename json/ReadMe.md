## <center> jsonCpp的相关配置
### * jsonCpp的下载和使用</br>
####  1.下载地址: [jsonCpp的下载地址](https://github.com/open-source-parsers/jsoncpp)</br>
####  2.编译不通过的解决方法:</br>
	* 编译器：vs2017 
	* 错误 MSB803 MSB804等等
	* 直接点击  项目=>重新解决方案目标（选择从父索引继承）
####  3.使用方法: [使用实例](https://www.cnblogs.com/kex1n/archive/2011/12/02/2272328.html)
	* 编译项目生成静态库(lib,头文件)
	* 使用编译的静态库即可

#### 遇到的问题：
* error LNK2038: 检测到“RuntimeLibrary”的不匹配项: 值“MDd_DynamicDebug”不匹配值“MTd_StaticDebug” </br>
 运行库设置的问题:</br>
 项目属性 -> 配置属性 -> C/C++ -> 代码生成 -> 运行库,  都设置一样就行了 多线程调试(/MTd)
* error:JsonCPP Use ChaReader and CharReaderBuild instead</br>
	解决办法：打开文件reader.h，找到
“class JSONCPP_DEPRECATED("Use CharReader and CharReaderBuilder instead") JSON_API Reader {”，
替换为“class  Reader {”，
即去掉“JSONCPP_DEPRECATED("Use CharReader and CharReaderBuilder instead") JSON_API”
