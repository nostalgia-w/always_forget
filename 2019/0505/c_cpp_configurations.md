# c_cpp_configurations in VS code

## 问题描述

使用vscode打开别的软件建立的工程文件，比如iar、keil等其他的软件的工程文件的文件夹，总是会遇到*.c或者*.h文件找不到的问题，或者某个宏定义没定义的问题。  

文件找不到一般是因为路径设置的问题，宏定义没定义就会提示宏没定义。  

在使用iar、keil的时候，建立项目的时候都会先进行设置，其中设置里就会有关于文件路径的设置，或者有些是软件默认设置的路径。还有一些宏定义，也是在设置里进行定义，或者有些是软件默认定义的。  

## 解决方法

遇到这种情况，需要在vs code的.vscode文件夹内增加一个c_cpp_configurations.json的文件。  

打开项目文件夹后，使用快捷键Ctrl+Shift+P调出控制窗口，再输入edit或者configuration，选择"C/Cpp:Edit Configurations"，就会在.vscode内生成一个c_cpp_configurations.json的文件。  

```json
{
    "configurations": [
        {
            "name": "Win32",
            "includePath": [
                "${workspaceFolder}/**"
            ],
            "defines": [
                "_DEBUG",
                "UNICODE",
                "_UNICODE"
            ],
            "windowsSdkVersion": "10.0.17763.0",
            "compilerPath": "C:/Program Files (x86)/Microsoft Visual Studio/2017/BuildTools/VC/Tools/MSVC/14.16.27023/bin/Hostx64/x64/cl.exe",
            "cStandard": "c11",
            "cppStandard": "c++17",
            "intelliSenseMode": "msvc-x64"
        }
    ],
    "version": 4
}
```

在"includePath"内添加需要的路径，在"defines"内添加需要的宏定义。  

## 参考链接

[visual studio code 提示 variable "uint32_t" is not a type name](https://www.jianshu.com/p/209327ad2e7a)