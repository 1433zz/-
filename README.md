# -
#导入numpy库
import numpy as np
#导入绘图工具库
import matplotlib.pyplot as plt
# np的linspace函数在指定的间隔范围内返回均匀间隔的一组数值
# 例如：np.linspace(start,end,n=50),在start- end,均匀的返回n个数值
# 定义了一个numpy的数组x，从-2π到2π，共200个值
x=np.linspace(-2*np.pi,2*np.pi,200,endpoint=True)
#对x进行cos计算
cos= np.cos(x)
#设置cos图像的线条颜色、线条粗细和图像标签标签
plt.plot(x,cos,color='red',linewidth=1.5,label='cos')
#对x进行sin计算
sin= np.sin(x)
#设置sin图像的线条颜色、线条粗细和图像标签标签
plt.plot(x,sin,color='blue',lw=2.5,label='sin')
#设置图例显示位置
plt.legend(loc='lower left')

#设定x轴范围
plt.xlim(-2*np.pi*1.1,2*np.pi*1.1)
#设定y轴范围
plt.ylim(cos.min()*1.1,cos.max()*1.1)

#设置X轴刻度值
plt.xticks(
    [-2*np.pi,-3*np.pi/2,-np.pi,-np.pi/2,0,np.pi/2,np.pi,3*np.pi/2,2*np.pi],
    [r'-$2\pi$',r'-$3\pi/2$',r'-$\pi$',r'-$\pi/2$','0',r'$\pi/2$',r'$\pi$',r'-$3\pi/2$',r'$2\pi$']
        )

#设置Y轴刻度值
plt.yticks([-1,0,1])
#通过plt.gca()获取坐标轴对象 然后设置属性
ax=plt.gca()
#隐藏top和right周
ax.spines['top'].set_color("none")
ax.spines['right'].set_color("none")
#把左下设置为0点
ax.spines['left'].set_position(('data',0))
ax.spines['bottom'].set_position(('data',0))

plt.show()
