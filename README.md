# AS-24000TP-100W-B-V30
PD 100W Board

前期准备：
          补焊DCDC 7533， DC3.3V降压芯片，给单片机供电（原本给东软芯片供电）
          补焊DCDC 7550， DC5.0V降压芯片，给UDP300主控和协控供电
          补焊SC8102A，USBA口主供电电源芯片
          准备测试单片机 STM32F103C8T6 模拟东软芯片，及 STLINK 烧录器烧录测试固件
          焊接飞线
          
脚位定义： PB0 ，UDP300电源供电控制脚
          PB6 ，I2C SCL
          PB7 ，I2C SDA

已实现：   USBA 15W 口输出， USBA18W 口输出， PD65W口输出， PD100W 输入、输出

已知问题： 由于7533是长供电，所以单片机处于长期工作状态，建议在P+P-和电池加装开关。
          充电完成后 PD 100w 口不断重启，猜测是 UDP300 切换充放电引起。
          单片机未处理其它IO，未实现电压电流检测，未实现188数码管电量显示功能。
         
