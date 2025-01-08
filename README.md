一、函数定义
在Bash中，函数的定义格式如下：

function function_name() { 
    # 函数体内容，这里可以包含各种Bash命令 
    echo "This is a function" 
} 
或者也可以使用如下简化形式：

function_name() { 
    echo "This is a function" 
} 
二、函数调用
定义好函数后，可以像调用命令一样调用函数。例如：

function_name 
三、函数参数
传递参数
在Bash函数中，可以向函数传递参数。函数内部可以通过$1、$2、$3等变量来获取传递进来的参数，其中$1表示第一个参数，$2表示第二个参数，以此类推。
示例：
function print_args() { 
    echo "The first argument is: $1" 
    echo "The second argument is: $2" 
} 
print_args "arg1" "arg2" 
参数个数
可以使用$#变量来获取传递给函数的参数个数。
示例：
function count_args() { 
    echo "The number of arguments is: $#" 
} 
count_args "arg1" "arg2" "arg3" 
四、函数返回值
使用return语句
在Bash函数中，可以使用return语句返回一个整数值。这个整数值的范围是0 - 255。
示例：
function add() { 
    local num1=$1 
    local num2=$2 
    local sum=$((num1 + num2)) 
    return $sum 
} 
add 2 3 
echo $?  # $? 用于获取上一个命令（这里是函数调用）的返回值 
使用变量输出结果
如果要返回更复杂的数据（如字符串等），可以使用变量来存储结果，然后在函数外部获取该变量的值。
示例：
function get_greeting() { 
    local greeting="Hello, World!" 
    echo $greeting 
} 
result=$(get_greeting) 
echo $result 
