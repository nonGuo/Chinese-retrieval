# 笔画方位检字法

### 笔画编码

* 平笔：横竖撇捺依次对应数字 1,2,3,4
  * 提与撇的书写方向相反，但笔形的倾角类似，归为笔画撇，对应数字3。
  * 点有两种笔形，编码规则同笔画提，对应数字3或4，视具体情况而定。如卜中的点对应4。
* 折笔：起笔+5+终笔
  * 横折竖(㇕)  : 起笔为横，终笔为竖，编码为152
  * 横折竖折横(㇅)：起笔为横，终笔为横，编码为151
  * 起笔或终笔不为横竖撇捺，根据笔形方向对应
  * 具体编码见[折笔编码表](#折笔编码表)
* 重复笔画用数字0表示 

---

###  检索步骤

* 独体字：四角 + 附笔
* 复合字：从外到内，从上到下，从左到右

具体如下：

> 独体字指无法从中拆出其他汉字的这一类汉字
>
> 1. 选择汉字最上方笔画，如有多笔则选择最左笔画。
> 2. 选择汉字最上方笔画，如有多笔则选择最右笔画。
> 3. 选择汉字最下方笔画，如有多笔则选择最左笔画。
> 4. 选择汉字最下方笔画，如有多笔则选择最左笔画。
> 5. 排除步骤3和步骤4选择的笔画，重复步骤4。

以升字为例：

<div style="display: flex"><img src=".\src\32301\1.svg" alt="升1" width="52" /><img src=".\src\32301\2.svg" alt="升2" width="52" /><img src=".\src\32301\3.svg" alt="升3" width="52" /><img src=".\src\32301\4.svg" alt="升4" width="52" /><img 	src=".\src\32301\5.svg" alt="升5" width="52" /></div>

​	依次选择笔画撇，竖，撇，竖，横，对应编码为<a>32301</a>

> 复合字值可以拆出独立汉字的一类汉字
>
> * 通过多次拆分得到一系列独体字和字根
> * 每次拆分只能拆成两部分，且必须为内外、上下或左右两部分，分别对应包围结构、上下结构和左右结构
> * 每次拆分出的两部分必须至少有一个汉字，且只要拆分出的汉字能继续拆分就必须继续拆分
> * 按照从外到内，从上到下，从左到右的顺序依次表示独体字或字根，编码间用 <a>半角逗号(,)</a> 隔开
> * 字根的编码方式与独体字相同

以羡字为例：

<div style="display: flex"><img src=".\src\羡\0.svg" alt="羡0" width="52" /><img src=".\src\羡\1.svg" alt="羡1" width="52" /><img src=".\src\羡\2.svg" alt="羡2" width="52" /><img src=".\src\羡\3.svg" alt="羡3"width="52" /></div>

1. 拆分上下两部分，其中下半部分为汉字<a>次</a>，上半部分编码为<a>43102</a>
2. 对<a>次</a>继续拆分，拆为左右两部分，其中右半部分为汉字<a>欠</a>，左半部分编码为<a>40300</a>
4. 对这三部分依次编码，得到羡的编码为<a>43102,40300,3034153</a>

以赢字为例：

1. 拆成“亡”“口”“月”“贝”“凡”五部分
2. 按照从外到内，再从上到下，最后从左到右的顺序表示这一系列汉字，顺序为“亡、口、月、贝、凡”
3. 得到赢字编码为<a>4025101,2152001,315411,2152340,3152004</a>

---

### 笔画位置判断规则

> 最上方笔画指笔画的起笔或终笔都不低于其他笔画，可以有多个。最下方笔画同理。

两笔画相连，即笔画交点至少为其中一笔画的起点或终点时：

1. 交点都是两笔画的起点或终点，视为等高
2. 否则，把交点不为笔画端点的那一笔视为最上方或最下方笔画

汉字 <a>口</a> 对应情况1：最上方笔画为竖和横折竖，最下方笔画为竖、横和横折竖。

汉字 <a>不</a> 对应情况2：最上方笔画为横

汉字 <a>上</a> 对应情况2： 最下方笔画为横

若两笔画无交点，且无明确上下位置关系，则视为等高。

汉字 <a>木 </a>的最下方笔画为撇、竖和捺。

---

### 笔画形变规则

> 拆出的字根为独体字变形，按原字形编码

1. 左边部件最下方笔画只有笔画横，改为提。
2. 捺笔的右侧存在笔画，改为点。

---

### 独体字重码率

对常用字中294个独体字进行了编码，结果如下：

| 对应汉字数量 | 编码数量 |
| :----------- | :------- |
| 8            | 1        |
| 5            | 1        |
| 4            | 5        |
| 3            | 12       |
| 2            | 24       |
| 1            | 177      |

| 编码    | 对应汉字                |
| :------ | ----------------------- |
| 20340   | 本 虫 来 木 末 未 耒 束 |
| 30041   | 大 夫 夹 丈 央          |
| 30201   | 年 千 午 乍             |
| 30102   | 重 垂 丘 壬             |
| 30342   | 秉 乘 禾 爪             |
| 3021521 | 白 自 舌 囱             |
| 3025401 | 乎 手 乌 鸟             |

---

### 折笔编码表

| 笔形 | 名称 | 号码 | 例字 |
| :----: | :----: | :----: | :----: |
| ㇕ | 横折竖 | 152 | 口 马 丑 |
| ㇇，㇖ | 横折撇 (横钩) | 153 | 又 了 |
| ㇗，㇄ | 竖折横 (竖弯横) | 251 | 山 母 |
| ㇚，㇁ | 竖钩(弯竖钩) | 254 | 于 犭|
| ㇙ | 竖折提 | 253 | 长 瓦 叫 |
| ㇜ | 撇折横 | 351 | 公 乡 |
| ㇛ | 撇折点 | 354 | 女 巡 |
| ㇢ | 撇折钩 | 453 | 乄 |
| ㇂，㇃ | 捺钩(扁捺钩) | 151 | 代 戈 心 |
| ㇅，㇍ | 横折竖折横(横折竖折弯) | 153 | 凹 朵 |
| ㇊ | 横折竖折提 | 154 | 计 鸠 |
| ㇆ | 横折竖钩 | 153 |同 也 |
| ⺄ | 横折捺钩 | 252 | 飞 风 |
| ㇞ | 竖折横折竖 | 253 | 鼎 |
| ㄣ | 竖折横折撇 | 253 | 专 |
| 乚 | 竖弯钩 | 252 | 已 电 |
| ㇎ | 横折竖折横折竖 | 152 | 凸 |
| ㇋ | 横折竖折横折撇 | 153 | 及 |
| ㇈ | 横折竖弯钩 | 152 | 几 |
| 乙 | 横折撇弯钩 | 152 | 亿 |
| ㇌ | 横折撇折弯竖钩 | 154 | 阳 |
| ㇉ | 竖折横折竖钩 | 254 | 马 号 |
| ㇡ | 横折竖折横折竖钩 | 154 | 乃 杨 |
