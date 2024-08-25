# Cascader
基于jQuery，样式模仿ElementUI的级联选择器
Original Plugins https://www.jqueryscript.net/form/cascading-selection-box.html

### 使用说明

``` html
  <input type="text" id="test"/>
```
``` js
  <script src="./jquery.min.js"></script>
  <script src="./cascader.js"></script>
```

``` js
  $('#test').zdCascader({
    data: citys, // 数据源
    container: '#test', // input框ID
    search: true, // 是否支持搜索
    onChange: function(value, label, datas){ // 选择监听
      console.log(value, label, datas);
    }
  });
  // other option with class i use fontawesome
  iconSelected:'fontawesome and other icons your like' //
  iconPostfix:'fontawesome and other icons your like insert arrow-right class' // in this please add "arrow-right" or "icon-right" or yout adjusted with css otherwise the layout will be messy, find zd-cascader-node__postfix.
  // Select Data By ID
	$('#test').zdCascader('select', [2, 22, 222]);
  // Open
	$('#test').zdCascader('open');
  // Close
	$('#test').zdCascader('close');
  // get id from search and by clicked
  let id = ($.isArray(label.value)) ? label.value.slice(-1)[0] : label.value;
  // get id from search
  if ($.isArray(label.value)) {
    let ids = datas[0].value;
    // reconstruct data
    $('#test').zdCascader('reload');
    $('#test').zdCascader('select', ids);
  } else {
    // get id from select data
    let ids = datas.map(item => item.id).sort();
  }
```