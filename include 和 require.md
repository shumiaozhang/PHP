## 引入

- include
- include_once
- require
- Require_once

include 如果引入时出现错误，会报一个警告错误，但程序还是会往下执行。而require会报一个致命错误，不会接着往下执行了。

include 在引入时，可以一下子引入多次，但include_once在引入时只能引入一次。

PHP文件一般引入时用require_once。

- include 系列
  - `include` 用于导入外部文件, 允许重复导入, 出现文本错误只是警告, 脚本会继续运行
  - `require` 用于导入外部文件, 允许重复导入, 出现文本错误抛出 **致命错误**, 脚本 **不会** 继续运行
  - `include_once` 用于导入外部文件, 只导入一次, 出现文本错误只是警告, 脚本会继续运行
  - `require_once` 用于导入外部文件, 只导入一次, 出现文本错误抛出 **致命错误**, 脚本 **不会** 继续运行
- 使用建议( 个人 )  
  - 1. 导入的时候, 首先使用 once 命令, 除非有明确的要求 会 重复导入
  - 1. 导入 html 公共部分, 建议使用 `include_once`
  - 1. 导入 php 脚本建议使用 `require_once`

       

