# XLNing
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <script type="text/javascript">
        function operation() { //获取文本框中的值并进行判断和运算
            var x = document.getElementById("var_x").value;
            var y = document.getElementById("var_y").value;
            var operator = document.getElementById("operator").value;
            var answer;
            if(x == "" || y == "")
            {
                alert("请输入正整数后进行计算操作！");
            } else{
                x = parseInt(x);
                y = parseInt(y);
                switch(operator)
                {
                    case '+':
                        answer = x + y;
                        break;
                    case '-':
                        answer = x - y;
                        break;
                    case '*':
                        answer = x * y;
                        break;
                    case '/':
                        if(y == 0)
                        {
                            alert("被除数不能为0，请重新输入！");
                            break;
                        }else{
                            answer = x / y;
                            break;
                        }
                }
                document.getElementById("result").value = answer;
            }
        }

        function clean(){ //文本框中的值清空，操作符恢复为“+”
           document.getElementById("var_x").value = '';
           document.getElementById("var_y").value = '';
            document.getElementById("operator").value = '+';
           document.getElementById("result").value = '';
        }
    </script>
</head>
<body>
    <table border = '1' align="center">
        <tr>
            <td align="right">请输入一个正整数x:</td>
            <td><input type="text " name = "var_xx" id="var_x"></td>
        </tr>
        <tr>
            <td align="right">请输入一个正整数y:</td>
            <td><input type="text " name = "var_yy" id = "var_y"></td>
        </tr>
        <tr>
            <td align="right">请选择操作符:</td>
            <td>
                <select id="operator">
                    <option name="operators"  value ="+" selected>+</option>
                    <option name="operators"  value ="-">-</option>
                    <option name="operators"  value ="*">*</option>
                    <option name="operators"  value ="/">/</option>
                </select>
            </td>
        </tr>
        <tr>
            <td align="right">运算结果为:</td>
            <td><input type="text " name = "result_n" id = "result"></td>
        </tr>
        <tr>
            <td colspan="2"  align="center">
                <button type="button" id="operationbtn" onclick="operation();">运算</button>
                <input type="button" id="clearbtn" value="清空" onclick="clean();"/>
            </td>
        </tr>
    </table>
</body>
</html>
