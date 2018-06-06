# canvas-handbook
canvas速查手册

> 规则：canvas指代canvas元素，ctx指代context.getContext('2d')对象，gl指代context.getContext('webgl')对象，xx和xxx用于占位

## 基础
* canvas.getContext(String)
说明：获取画板上下文
参数：'2d', 'webgl'
  

## 2d画板  

### 填充-fill
* ctx.fillStyle = 'rgba(0, 0, 225, 1.0)'  
说明：设置填充颜色
* ctx.fillRect(x, y, width, height)  
说明：填充一个矩形  
参数：x：左上角x坐标，y：左上角y坐标，width：宽度，height：高度

## webgl
### clear
* gl.clearColor(red, green, blue, alpha)  
说明：设置清空颜色缓冲区的颜色  
参数：所有参数取值返回0~1  

* gl.clear(mask)
说明：清空画板
参数：一个GLbitfield按位OR掩码，指示要清除的缓冲区。可能的值是gl.COLOR_BUFFER_BIT，gl.DEPTH_BUFFER_BIT，STENCIL_BUFFER_BIT（[摘自mdn](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/clear)）
### create-创建相关
* gl.createShader(type)  
说明：用于创建WebGLShader对象  
参数：gl.VERTEX_SHADER（顶点着色器） 或 gl.FRAGMENT_SHADER（片元作色器）  
返回值：WebGLShader对象  

* gl.shaderSource(shader, source)  
说明：设置着色器源码  
参数：shader: WebGLShader对象，source: 着色器源码  

* gl.compileShader(shader)  
说明：编译着色器为二进制代码，以便WebGLProgram使用
参数：WebGLShader对象

* gl.createProgram()  
说明：创建并初始化一个 WebGLProgram 对象  
返回值：一个 WebGLProgram 对象，该对象由一个顶点着色器和一个片元着色器组成  

* gl.attachShader(program, shader)  
说明：为 WebGLProgram 对象添加一个着色器  
返回值：program：WebGLProgram对象，shader：WebGLProgram对象  

* gl.linkProgram(program)  
说明：链接 WebGLProgram 中的片元着色器和顶点着色器  
参数：WebGLProgram 对象  

* gl.useProgram(program)  
说明：设置 WebGLProgram  
参数：WebGLProgram 对象


### get
* gl.getShaderParameter(shader, pname)  
说明：获取给定WebGLShader的信息  
参数：shader：WebGLShader对象，pname：要查询的信息。gl.DELETE_STATUS（着色器是否被删除），gl.COMPILE_STATUS（着色器是否编译完成），gl.SHADER_TYPE（着色器类型）  
返回值：根据pname不同，返回boolean或者string  

* gl.getShaderInfoLog(shader)
说明：返回指定WebGLShader对象的信息日志。它包含警告，调试和编译信息。
参数：WebGLShader对象  
返回值：错误信息

* gl.getProgramParameter(program, pname)
说明：获取给定 WebGLProgram 的信息  
参数：program：给定的 WebGLProgram，pname：需要获取的信息类型。gl.DELETE_STATUS（是否被删除）、gl.LINK_STATUS（连接是否成功）、gl.VALIDATE_STATUS（指示上次验证​​操作是否成功）、gl.ATTACHED_SHADERS（程序所附加的着色器数量）、gl.ACTIVE_ATTRIBUTES（程序的活动属性变量的数量）、gl.ACTIVE_UNIFORMS（程序的活动统一变量的数量）（WebGL2 还有更多值，[参考mdn](https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getProgramParameter)）  
返回值：根据pname不同，返回不同类型的值  

* gl.getProgramInfoLog(program)
说明：返回program的日志    
参数：WebGLShader对象  
返回值：日志信息  

* gl.getAttribLocation(program, name)  
说明：返回给定 WebGLProgram 的 attribute 属性的位置  
参数：program：WebGLProgram对象，name：attribute类型的属性名  
返回值：所获取变量的地址

* gl.getUniformLocation(program, name)  
说明：返回给定 WebGLProgram 的 uniform 属性的位置  
参数：program：WebGLProgram对象，name：uniform类型的属性名  
返回值：所获取变量的地址

### set
* gl.uniform4f(index, v0, v1, v2, v4)  
说明：设置uniform属性  
参数：index：变量地址

* gl.vertexAttrib3f(index, v0, v1, v2)  
说明：设置顶点属性  
参数：index：变量地址

### draw 绘制
* gl.drawArrays(mode, first, count)  
说明：从向量数组中绘制图元  
参数：mode：指定绘制图元的方式 gl.POINTS（绘制点）、gl.LINE_STRIP（绘制一系列线段，上一点连接下一点）、gl.LINE_LOOP（绘制一系列线段，上一点连接下一点，并且最后一点与第一个点相连）、gl.LINES（绘制一系列单独线段。每两个点作为端点，线段之间不连接）、gl.TRIANGLE_STRIP（绘制一个三角带。）、gl.TRIANGLE_FAN（绘制一个三角扇）、gl.TRIANGLES（绘制一系列三角形。每三个点作为顶点）。first：指定从那个点开始绘制。count：指定绘制需要多少个点


### delete 删除
* gl.deleteShader(shader)  
说明：标记要删除的shader，当shader不在使用时将被删除  
参数：WebGLShader 对象

* gl.deleteProgram(program)  
说明：删除给定的WebGLProgram，如果当前WebGLProgram已删除，则此方法无效  
参数：WebGLProgram对象



### 着色器
