# jquery-checkAll
一个基于jQuery的全选控制插件

### 怎么用？
把jquery-checkAll.js下到你本地，后于jQuery引入.

    <script src="js/jquery-checkAll.js"></script>
    
  
接下来准备一个列表：  

    <input id="checkAll" type="checkbox" /> 全选
    <ul>
        <li><input class="slaves" value="1"/></li>
        <li><input class="slaves" value="2"/></li>
        <li><input class="slaves" value="3"/></li>
        <li><input class="slaves" value="4"/></li>
    </ul>
    <!--js部分-->
    <script>
        $("#checkAll").checkAll(".slaves");
    </script>
    
  
现在基本效果就已经出来了，可以更加复杂一点

    <!--js部分-->
    <script>
        var checked;//选中项的value值集合
        $("#checkAll").checkAll(".slaves",{
          //选中事件回调，data参数为已选中的slave元素的jQuery对象
          onChecked : function(data){
            checked = new Array();
            data.each(function(){
                checked.push($(this).val());
            })
          }
        });
    </script>
    
  
第二种方式适合ajax应用，毕竟全选的目的就是提取选中行的id，通过onChecked事件，将id推入checked数组。

  
  
