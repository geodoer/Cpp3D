> Cpp3D工程 
>
> 包含C++基础语法、Qt、3D数学基础、计算几何等内容。



# 工程相关

在工程中添加子模块（以`core`模块为例）：

1. 为子模块创建头文件目录：`include\core`
2. 创建子工程`core`到`submodules\core`目录下，后将`submodules\core\core`重命名为`v141`，删除`core.cpp`
3. 为子模块添加源代码目录：`submodules\src`

项目配置：

1. 输出目录：`$(SolutionDir)bin\$(Platform)\$(Configuration)\`

2. 中间目录：`$(SolutionDir)tempfiles\$(PlatformName)\$(Configuration)\$(ProjectName)\`

添加第三方库（添加库时要注意`配置`和`平台`，以`boost`为例）

1. 将第三方库放至`3rdlib`目录下
2. include目录
   1. 切换到`所有配置`、`所有平台`
   2. 在`C/C++ -> 常规 -> 附加包目录`添加`$(SolutionDir)3rdlib\boost_win\include`
3. lib目录
   1. 切换到`debug`、`x64`
   2. 在`链接器 -> 常规 -> 附加库目录`中添加`$(SolutionDir)3rdlib\boost_win\$(Platform)\$(Configuration)`
4. 添加lib文件
   1. 更改`list_lib_fn.bat`中的代码，列出lib文件的所有文件名
   2. 切换到`debug`、`x64`
   3. 在`链接器 -> 输入 -> 附加依赖项 -> 添加lib文件的名字`
5. 将dll文件放到`bin`下

