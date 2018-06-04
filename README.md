# canvas-handbook
canvas速查手册

> 规则：canvas指代canvas元素，ctx_2d指代context.getContext('2d')对象，ctx_gl指代context.getContext('webgl')对象，xx和xxx用于占位

## 基础
* canvas.getContext(String)
说明：获取画板上下文
参数：'2d', 'webgl'
  

## 2d画板  

### 填充-fill
* ctx_2d.fillStyle = 'rgba(0, 0, 225, 1.0)'  
说明：设置填充颜色
* ctx_2d.fillRect(x, y, width, height)  
说明：填充一个矩形  
参数：x：左上角x坐标，y：左上角y坐标，width：宽度，height：高度
