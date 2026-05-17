# Python 教學講義
###### tags: `tutor` `python`
本文所有內容與資料皆由本人蒐集與撰寫，轉載請註明出處。

- [Python 練習題](https://hackmd.io/UG_GPvJFRs2NUQk2r-3Mlg?view)
- 參考[官方中文教學文件](https://docs.python.org/zh-tw/3/tutorial/index.html)
 

## Overview
程式語言分為高階語言、組合語言、機器語言等等，Python屬於高階語言的一種。機器語言與組合語言直接控制電腦硬體，但難以閱讀與開發；高階語言易於閱讀與開發，但需要「翻譯」給電腦聽。

> 來自 Python 官方網站的介紹：
> Python 是一種易學、功能強大的程式語言。它有高效能的高階資料結構，也有簡單但有效的方法去實現物件導向程式設計。Python 優雅的語法和動態型別，結合其直譯特性，使它成為眾多領域和大多數平臺上，撰寫腳本和快速開發應用程式的理想語言。

常見應用：網站開發、資料分析、機器學習、遊戲開發、網路爬蟲...
其他語言：C、C++、R、Java、JavaScript、SQL、Go、Ruby......


### 學習地圖
以臺大資工系必修為例：
![](https://i.imgur.com/Y2AdRO3.png =80%x)
以臺大資管系必修為例：
![](https://i.imgur.com/aC9lfrs.png =70%x)


## Python 入門
### 環境建置
 - 互動模式
     - Open Terminal（終端機） and input 'python'
     - Execute each line directly
     - If Python is not installed, go to [Python official website](https://www.python.org/downloads/)
    ```
    >>> 1 + 2
    3
    ```
 - 腳本模式
     - Need interpreter（直譯器） to help 'translate'
     - Execute the whole file or block at once
     - VSCode 示範 - .py 檔 與 .ipynb 檔
    ```python=
    for i in range(3):
        print(i)
    print("The loop ends.")
    ```
    ```
    Output：
    0
    1
    2
    The loop ends.
    ```
 - [VSCode 安裝教學](https://www.citerp.com.tw/citwp2/2021/12/22/vs-code_python_01/)
> 補充：[使用 Anaconda 來建置開發環境](https://medium.com/ccclub/ccclub-python-for-beginners-tutorial-c23859d2bde4)

### 基礎語法（Basic Syntax）
 - Our first program: `print("Hello World!")`
     - `print()` 是一個函數 （function）
     - "Hello World!" 是給予這個函數的輸入
     - 此函數會幫助我們印出給定的輸入，給使用者看
#### 計算（Computation）
```
>>> # This is a comment（註解）
>>> # A comment will not be executed by python
>>> 1 + 2
3
>>> 3 - 1
2
>>> 5 * 2
10
>>> 5 ** 2      # 5 的 2 次方
25
>>> 8 / 5       # 8 除以 5（回傳小數）
1.6
>>> 8 // 5      # 8 除以 5 的商
1
>>> 8 % 5       # 8 除以 5 的餘數（取 mod）
3
>>> (50 - 5 * 6) / 4
5.0
```


#### 變數（Variable）
- 我們會需要變數來存放數值運算的結果，使用 `=` 可以將數值指派給變數，可以參考 [基本命名規則](https://ithelp.ithome.com.tw/articles/10217188)
- 若重複指派給相同名稱的變數，原本的值會被覆蓋掉！
- `a = 10` 意為指派 10 給 a（右邊的值丟給左邊的容器）
- `a == 10` 意為比較 a 是否等於 10（為邏輯判斷式）
```
>>> width = 20
>>> height = 5 * 9
>>> width * height
900
```
- 讀取變數
```
>>> var = input()
3   # 使用者自行輸入
>>> print(var)
3   # 電腦將 var 的值印出
```
 > 進階：[Python 下劃線的意義](https://zhuanlan.zhihu.com/p/36173202)
#### 資料類別（Data Type）
 - 在宣告變數時，Python 自動幫我們決定資料類別
 - 其他語言（如 C++） 可能需要做類別宣告：`int a = 1`
 - 常見的基礎資料類別如下：
     - 整數 integer - `3`
     - 小數（浮點數） float - `3.0`
     - 字母 character - `'a'`
     - 字串 string - `"This is a string"`
     - 布林值 boolean - `True` (Non-zero) / `False` (Zero)
 > 補充：String 是由 Character 組成的陣列，其他語言有可能會將 String 與 Character 當作兩種資料類別，但在 Python 中沒有 Character 的概念，因此長度為一的字母在 Python 中也會被當成字串來做處理。

#### 型別轉換（Casting）
```
>>> str(3)
'3'
>>> int("3")
3
>>> float(3)
3.0
>>> float("string")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: could not convert string to float: 'string'
>>> type(3)  # 檢查資料類別
<class 'int'>
```
#### 指派 & 自我指派 （Assignment & Self-assignment）
```python=
a = 10
print(a)
a = a + 2    # 把 a + 2 指派給 a
print(a)
a += 2       # a 自己等於自己 + 2
print(a)
```
```
Output:
10
12
14
```
> 相同的還有 `-=` `/=` `*=` `//=` `**=` `%=` ...

#### 比較/邏輯運算元（Comparison & Logical Operators）
 - < / <=：小於 / 小於等於
 - \> / >=：大於 / 大於等於
 - == / !=：等於 / 不等於
 - `and`：且
 - `or`：或
 - `not`：非

### 寫程式的流程（Workflow）
 - Debug：在我們遇到各種 Error 時，需要去檢查程式哪裡寫錯
 - 有時候是語法錯、有時候是邏輯錯...
 - 整體的寫程式流程：
![](https://i.imgur.com/kDs6oep.png =50%x)

### 電腦架構
非常簡易版的架構圖如下：
 - Input：鍵盤、滑鼠、觸控螢幕、麥克風等等
 - Output：螢幕、喇叭、印表機等等
 - Storage：硬碟、光碟機等等
 - CPU（中央處理器）：負責電腦的大部分運算
 - Memory：電腦內暫存的記憶體空間
 > 補充 - GPU（顯示卡）：負責遊戲、3D繪圖、機器學習等等運算
 > 若對這個有興趣的話，可以去查「計算機結構」或修相關課程

![](https://i.imgur.com/pmeyrcm.png =40%x)

### 二進位制
 - 電腦使用二進位制來儲存數值，簡易的對照如下圖
 > 若對這個有興趣的話，可以去查「數位邏輯」、「電路學」或修相關課程

![](https://i.imgur.com/o0VuIPk.png =30%x)

### 排版方式（Formatting）
一些排版準則如下：
 - 通常在運算元前後會空白
 - 在每個區段的 code 前後會空行，才不會全部擠在一起不好分辨
 - 變數命名要有意義，讓別人也看得懂你在寫什麼
 - 加入註解提高程式易讀性，並說明撰寫邏輯、使用方法等等

寫程式除了讓他可以執行以外，讓別人看懂也是一件很重要的事情。
當未來需要進行多人的大型開發時，程式碼的簡潔易懂可以大大加快開發協作時間。
想了解更多可以搜尋 Google coding style 或 SOLID 原則。


## Python 基礎 (1)
### 條件判斷（Conditionals）
```python=
price = int(input())
if price < 100:
    print("It's cheap.")
elif price >= 100 and price < 200:
    print("It's okay.")
else:
    print("It's too expensive!")
```
 - 若...則... (`if`) ，否則若...則... (`elif`) ，若以上皆非則... (`else`)
 - `if` 跟 `else` 是一組的，後面要放條件判斷 or 布林值，`elif` 可有可無
 - 底下的指令則需縮排，讓 Python 知道哪些是條件成立需要執行的
 - 裡面還可以再包 `if-else` （巢狀條件判斷）
```python=
if ...
    if ...
        ...
    else
        ...
else ...
    if ...
        ...
    else
        ...
```
 - 另一種寫法：A `if` condition `else` B（若 condition 為真，則執行 A ，否則執行 B）
 - 重要：在 Python 中，縮排是很重要的，Python 會用縮排來判斷每行程式碼的所在層級，縮排不同，執行起來的結果有可能完全不同！




### 迴圈（Iterations）
 - 我們很常需要電腦幫我們做重複的工作
 - 迴圈就可以幫我們達到此目的
 - 迴圈基本上分為兩種語法： `while` 跟 `for`
 - `while` 可以想成不斷執行的 `if`，直到條件不再成立為止
     - 要小心「無窮迴圈」的發生
 - `for` 則是針對清單內的元素，每個都執行一次所有指令
     - 常搭配 range() 或是清單一起使用
```python=
i = 0
while i < 3:
    print(i)
    i += 1
print("The loop ends.")
```
```python=
for i in [0,1,2]:  # Or for i in range(3):
    print(i)
print("The loop ends.")
```
```
Output：
0
1
2
The loop ends.
```
> 備註：`i` is called 'Loop Counter' in above examples
> For 迴圈會自動更新 Loop Counter，While 迴圈則不會

#### 無窮迴圈（Infinite Loop）
 - 當一個迴圈無法停止執行時，就稱為無窮迴圈
 - 無窮迴圈只能透過強制停止的方式來結束！（Ctrl + C）
 - 示範：
```python=
while 4 > 3:  # A always true condidtion 
    print('Loop')
```

#### Range()
上面的例子中有使用到 range()，而 range() 是能夠幫助我們創造一個範圍的函數，其用法為：
- `range(n)` 會回傳 `[0,1,2,...n-1]` 的清單
- `range(m,n)` 會回傳 `[m,m+1,m+2,...n-1]` 的清單
- `range(m,n,k)` 會回傳 `[m,m+k,m+2k,...]` 的清單，最後一個元素不超過 n-1

一般的情況下使用第一個就好。

> 備註：回傳型態其實不完全是清單，但我們先把它當成清單用就好
> 可以透過 `list()` 將其轉為清單

#### 巢狀迴圈（Nested Loop）
 - 迴圈裡也可以再放迴圈，很多複雜的程式都需要用到
 - 要注意各個迴圈的執行順序與邏輯，同時撰寫避免不必要的迴圈
```python=
for i in range(3):
    print(i)
    for j in range(2):
        print(">",j)
    print('=====')
```
```
Output:
0
> 0
> 1
=====
1
> 0
> 1
=====
2
> 0
> 1
=====
```


#### 迴圈特殊處理 - break & continue
 - `break`：跳出迴圈外，直接結束迴圈執行
 - `continue`：跳過後面的指令，直接結束此次迴圈，並進行下一次迴圈
 - 用以控制迴圈，給予迴圈多個「出口」
 - 若放在多重迴圈內，只會跳出一層迴圈
 - 要小心不要寫出沒有意義的 `break` & `continue`！
```python=
i = 0
while (i < 10):
    i += 1
    if i == 2:
        continue
    if i == 6:
        break
    print(i)
```
```
Output:
1
3
4
5
```


### 字串處理
 - 字串基本上可視為字母陣列 (Array)，基本操作如下：
```
>>> s = 'String'
>>> print(type(s))
<class 'str'>

>>> print(s[0])
'S'

>>> print(s[-1])
'g'

>>> print(len(s))
6

>>> print(s+s)
'StringString'

>>> print(s,s)
String String

>>> print(s+"&"+s)
String&String

>>> print(s*3)
StringStringString

>>> print(s.replace('Str','do'))
doing

>>> print(s.find('ing'))
3

>>> print(s.upper())
STRING

>>> print(s.lower())
string

>>> print('t' in s)
True
```

### 清單（List）
 - 清單是 Python 最常用、也最好用的資料類別，具順序性
 - 甚麼東西都可以裝，裝的東西也可以不同，也可以用清單包清單
 - 想成一個百寶袋，甚麼都可以塞，再拿出來
     - 32位python的儲存上限是536870912 個元素
     - 64位python的儲存上限是1152921504606846975 個元素
 - 前面提到的字母陣列其實概念跟清單很像

```
>>> l = [1, 1.0, 10, "test"]
>>> print(l[0])
1

>>> print(l[2])
10

>>> l[2] = 100
>>> print(l[2])
100

>>> print(l[-1])
"test"

>>> print(len(l))
4

>>> l.append("123")
>>> print(l)
[1, 1.0, 100, "test", "123"]

>>> l.pop()
"123"
>>> print(l)
[1, 1.0, 100, "test"]

>>> print(l + l)
[1, 1.0, 100, "test", 1, 1.0, 100, "test"]

>>> print(l * 3)
[1, 1.0, 100, "test", 1, 1.0, 100, "test", 1, 1.0, 100, "test"]
```
 - Traverse a list：
```python=
l = [1,2,3,4,5]
for i in l:   # or for i in range(len(l))
    print(i * 2)
```
```
Output:
2
4
6
8
10
```
- 常見操作（Common Operations，供參考）：
    | Method | Usage |
    | -----  | ----- |
    | list.append(x)  | Add element x to end of list. |
    | list.sort()   | Sort (order) the list. A comparison function may be passed as a parameter. |
    | list.reverse()  | Reverse the list. |
    | list.index(x)   | Returns index of first occurrence of x. |
    | list.insert(i, x)  | Insert x into list at index i. |
    | list.count(x)   | Returns the number of occurrences of x in list. |
    | list.remove(x)   | Deletes the first occurrence of x in list. |
    | list.pop(i)  | Deletes the ith element of the list and returns its value. |

#### List Copying
- 在複製 List 時，要特別留意以下狀況，並非正確的 List 複製方法：
```python=
# Wrong Copy (Reference Copy Only)
aList = [1, 2, 3]
anotherList = aList
anotherList[0] = 5
print(aList)
# Check their address
print(id(aList), id(anotherList))
```
```
Output:
[5, 2, 3]
1805364504896 1805364504896
```
 - 當我們修改 `anotherList` 時，原本的 `aList` 也一同被修改
 - 主要是因為 List 儲存的是記憶體參照（或是說 List 是可變物件，後面會提到），第三行做的事情僅僅是將參照傳給另一個變數，因此也可以發現他們的記憶體其實是相同的

##### How to copy a list correctly?
有以下幾種方式可以正確地複製 List：

```python=
# Correct Copy
aList = [1, 2, 3]
# Three different ways to copy a list (Shallow)
anotherList = list(aList)
anotherList = aList[:]
anotherList = aList.copy()

anotherList[0] = 5
print(aList)
# Check their address
print(id(aList), id(anotherList))
```
```
Output:
[1, 2, 3]
1805364505024 1805364643392
```

> 補充：此處使用的稱為「Shallow Copy」，僅複製容器中元素的地址
> 若連容器中的元素本身都想完全複製，需要使用「Deep Copy」
> 延伸閱讀： [Python - 淺複製(shallow copy)與深複製(deep copy)](https://ithelp.ithome.com.tw/articles/10221255)
    
    
### CSV（Comma-separated value）檔案
 - CSV 是常見的儲存資料格式
 - 簡潔、統一、格式化、方便處理
```
QuotaAmount,StartDate,OwnerName,Username
150000,2016-01-01,Chris Riley,trailhead9.ub20k5i9t8ou@example.com
150000,2016-02-01,Chris Riley,trailhead9.ub20k5i9t8ou@example.com
150000,2016-03-01,Chris Riley,trailhead9.ub20k5i9t8ou@example.com
150000,2016-01-01,Harold Campbell,trailhead14.jibpbwvuy67t@example.com
150000,2016-02-01,Harold Campbell,trailhead14.jibpbwvuy67t@example.com
150000,2016-03-01,Harold Campbell,trailhead14.jibpbwvuy67t@example.com
150000,2016-01-01,Jessica Nichols,trailhead19.d1fxj2goytkp@example.com
150000,2016-02-01,Jessica Nichols,trailhead19.d1fxj2goytkp@example.com
150000,2016-03-01,Jessica Nichols,trailhead19.d1fxj2goytkp@example.com
```

結合前面的字串與清單處理方式，我們可以輕鬆的處理 CSV file 中的每一行資料：
```
>>> line = 'amount,date,owner,user'
>>> data = line.split(',')
>>> print(data)
['amount', 'date', 'owner', 'user']
>>> print(data[0])
amount
```
那如何處理整個 CSV file？使用檔案處理相關函數（之後再講）：
```python=
result = []
with open('file.csv') as f:
    data = f.read()
    lines = data.split('\n')
for line in lines:
    result.append(line.split(','))
print(result)
```
```
Output:
[[QuotaAmount,StartDate,OwnerName,Username],
[150000,2016-01-01,Chris Riley,trailhead9.ub20k5i9t8ou@example.com],
[150000,2016-02-01,Chris Riley,trailhead9.ub20k5i9t8ou@example.com],
...]
```

## Python 基礎 (2)
### 函數（Function）
我們以前寫 print('Hello') 時，其實就是在呼叫函數，這個函數會幫我們把我們傳入的 'Hello' 印出來。其他像是 range()、type()、input() 等也都是函數，各有不同的用途。

我們也可以透過特定語法來定義自己的函數，透過函數可以幫我們達成「模組化」，省去重複的 code 同時提供更多彈性來執行類似的動作。

一個函數包含名稱、本體、輸入（Input）與輸出（Output），後兩者又叫做參數（Parameters）與回傳值（Return Values）。有時我們也會在函數最一開始的地方加入註解，來說明函數的使用方式以及參數 / 回傳值類型。

![image](https://hackmd.io/_uploads/ByAuqF8kR.png =80%x)

以下圖為例，輸入是蘋果，輸出是切半的蘋果，函數 `h` 的作用是把蘋果切半。
![image](https://hackmd.io/_uploads/HJDXscDyA.png)


#### 名稱
- 用關鍵字 `def` 來宣告函數，名稱接在 `def` 後面
- 名稱通常會取與函數作用相關，便於使用者理解函數功能
- 使用函數時，用其名稱來呼叫函數

#### 本體
- 把要執行的程式碼包在函數本體中
- 有時會在本體前面加上註解，用以說明函數功能
    - 說明最好包含：輸入、輸出、作用
    - 因為函數沒有限制變數的類別，所以最好在說明中講清楚

#### 輸入（參數）
- **參數的作用是提供資料給函數操作**
- 函數的參數可以自行命名（如下例的 n）
- 可以傳入多個參數，用逗號隔開
- 可以給定預設值（如下例的 n = 5）

#### 輸出（回傳值）
- **回傳值的作用是把結果回傳給使用函數的人**
- 使用 `return` 來控制函數的結束點，並將回傳值放在後面
- 若沒有 `return` 則會自動在最後加上 `return None`
- 可放回傳多個結果，用逗號隔開
- 函數結束後會回到主程式，繼續執行後面的程式

以下是一個在 python 中的實際例子，輸入是一個數字 `n` ，輸出是一個清單 `alist` ，函數 `get_1_to_n` 的作用是獲取 1 ~ n 的清單。
```python=
def get_1_to_n(n = 5):
    print('Getting a list range from 1 to',n)
    alist = list(range(1,n+1))
    return alist

x = get_1_to_n(10)  # or get_1_to_n(n = 10)
print('X = ',x)
print('~~~~~~~~~~')
y = get_1_to_n()
print('Y = ',y)
```
```
Output:
Getting a list range from 1 to 10
X =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
~~~~~~~~~~
Getting a list range from 1 to 5
Y =  [1, 2, 3, 4, 5]
```
> 補充：[Python yield的用法詳解](https://medium.com/ai%E5%8F%8D%E6%96%97%E5%9F%8E/python-yield%E7%9A%84%E7%94%A8%E6%B3%95%E8%A9%B3%E8%A7%A3-%E8%BD%89%E9%8C%84-52f539b67bdf)
> 補充：[參數（Parameters）與引數（Arguments）的差異](https://notfalse.net/6/arg-vs-param)

#### 變數範圍（Scope of Variable）
變數依據生命週期的不同，分為全域變數與區域變數。
- 區域變數（Local Variable）
    - 定義在函數內的變數稱為區域變數
    - 只能在函數內使用，函數結束後變數也會跟著消失
- 全域變數（Global Variable）
    - 定義在函數外的變數稱為全域變數
    - 所有地方（包含函數內）都可以使用，直到程式結束執行才會消失
- 若函數內宣告與全域變數同名的變數，則會被當作是區域變數，對其進行的操作不影響全域變數
- 通常若我們需要拿到函數內的某個變數，我們會直接使用 `return var`
```python=
scale = 3 # Global

def multiply(num):
    return num * scale

def multiply_5(num):
    scale = 5 # Local
    return num * scale

print(scale)
print(multiply(2))
print(multiply_5(2))
print(scale)
```
```
Output:
3
6
10
3
```
> 補充：在函數內修改全域變數與上一層變數的方法：[Global & Nonlocal](https://ktinglee.github.io/LearningPython100days(6)_global_and_nonlocal/)

#### 可變物件（Mutable Object）與不可變物件（Immutable Object）
在 Python 中，不同資料類別又可以其性質分為可變物件與不可變物件。 

| 分類 | 可變物件  | 不可變物件 |
| ---- | -------- | -------- |
| 說明 | 被創造出來後，其值可以被改變的物件。 | 被創造出來後，其值無法被改變的物件。 |
| 舉例 | list, dict, set* | int, float, string, tuple |
| 修改 | 可以，依資料類別不同有不同修改方式，修改時記憶體位置不會改變。 | 無法，只能透過重新指派的方式，此時記憶體位置亦會被重新分配。 |


```python=
# Mutable Object
alist = [1,2,3]
alist = [4,5,6]  # Okay
alist[1] = 100  # Okay

# Immutable Object
astring = 'string'
astring = 'STRING' # okay
astring[1] = 'A' # TypeError: 'str' object does not support item assignment
```

接著我們來看看記憶體位址的變化：

```python=
# Let's take a look on the addresses of these objects
# id() is a function help finding address of a variable
# Mutable Object
alist = [1,2,3]
print(id(alist))
alist[1] = 100
print(id(alist))
print('=====')
# Immutable Object
astring = 'string'
print(id(astring))
astring = 'STRING'
print(id(astring))
```
```
Output:
1541330859072
1541330859072
=====
1541255790064
1541259351920
```


> 參考 [什麼是 Immutable & Mutable objects](https://www.maxlist.xyz/2021/01/26/python-immutable-mutable-objects/)
> \*關於 set 可不可變其實有點[爭議](https://stackoverflow.com/questions/14193438/are-python-sets-mutable)，在這裡先當作他是可變的
> 
#### Pass by Assignment - Example Illustration
此處我們「不會」深入講當傳參數時發生了什麼事情，因為牽扯到一些記憶體跟參照等等的概念，我們會用幾個例子來說明何謂 Python 的 Pass by Assignment。

Python 中函數依據傳入參數的類別不同，會有不同的行為。
- 當傳入參數可變物件時：
    - **若未經重新指派，而是在函數裡直接修改參數，則會原始變數的值也會一同被修改**
    - **若經重新指派，則視為全新的變數，原始變數不會被影響**
- 當傳入參數為不可變物件時：
    - **任何對參數的操作都不影響原始變數（除非使用全域變數方式修改）**

聽起來很複雜對吧？我們直接用例子來看會比較清楚一些：

```python=
def listchange(l):
    l[0] = 'A'
alist = [1,2,3]
listchange(alist)
print(alist)
```
```
Output:
['A',2,3]
```

```python=
def strchange(s):
    s = 'STRING'
astring = 'string'
strchange(astring)
print(astring)
```
```
Output:
string
```

在以上的例子中，`alist` 為可變物件，因此做為參數傳入並在函數中修改時，原始的 `alist` 也一同被修改；而 `astring` 為不可變物件，因此做為參數傳入時，我們並無法直接修改他的值，只能透過重新指派的方式給予 `'STRING'` 這個值，而原始的 `astring` 依然存放 `string` 這個值沒有改變。

我們在撰寫函數時，比較好的方式是不要直接修改原始參數的值，而是將修改後的值存放在新的變數中，並作為回傳值傳回給呼叫函數的地方，以避免混淆的狀況。

> 參考 [關於 Python 獨有的 Pass by Assignment](https://luka.tw/Python/%E5%9F%BA%E7%A4%8E%E6%95%99%E5%AD%B8/past/2021-09-21-is-python-call-by-sharing-122a4bf5a956/)，以及 [英文版本（Stackoverflow）](https://stackoverflow.com/questions/986006/how-do-i-pass-a-variable-by-reference)


#### 遞迴（Recursion） - An example on factorial
遞迴是一種概念，指的是「在函數在執行過程中呼叫自己」的方法。這種技術對於解決某些複雜問題特別有用，例如處理樹狀結構、遞迴搜尋、組合數學等。以下是遞迴的基本概念和特性:
1. 基礎案例（Base Case）：遞迴函數必須有一個基礎案例，也就是遞迴呼叫的終止條件。當滿足這個條件時，遞迴將不再進行，從而避免無限迴圈。
2. 遞迴案例（Recursive Case）：如果沒有滿足基礎案例的條件，函數就會進入遞迴案例。在這個案例中，函數會呼叫一個較小的子問題版本。
3. 問題簡化：遞迴案例通常將原始問題簡化為一個較小的子問題，直到滿足基礎案例為止。
```python=
def find_fact(n):
    if n == 1: # base case
        return 1
    else: # recursive case
        recurse = find_fact(n-1)
        result = n * recurse
    return result
```
![image](https://hackmd.io/_uploads/S1gBbY810.png)

> 補充：[遞迴深度的上限](https://clay-atlas.com/blog/2020/09/20/python-cn-recursionerror-maximum-recursion-depth-exceeded/)

關於函數還有很多可以講：Recursion 的設計方法、Call by Reference、Call by Value...。但有些東西太進階了，我們先停在這裡，以後有機會或是遇到的時候再細講。



### 其他常見資料結構
#### 元組（Tuple）
 - 與 list 類似，但是屬不可變物件
 - 不同於 list 使用 `[]` ，tuple 使用 `()` 
 - 一個元素的 tuple 須以 `(item, )` 表示
 - 因屬不可變物件，故僅能以重新指派的方式修改其值，如下例：
```
>>> mytuple = (11, 22, 33)
>>> saved = mytuple
>>> mytuple += (44,)
>>> mytuple
(11, 22, 33, 44)
>>> saved
(11, 22, 33)
```
 - zip()
```python=
num = [1,2,3]
char = ['a','b','c']
CHAR = ['A','B','C']
for i in zip(num, char, CHAR):
    print(i)
```
```
Output:
(1, 'a', 'A')
(2, 'b', 'B')
(3, 'c', 'C')
```

#### 字典（Dictionary）
當我們需要了解某個字的讀音時，我們會去查找字典，在其中尋找對應的讀音。這種 {字: 讀音} 的配對，在 Python 中可以透過字典來實現。
 - 字典的組成包含鍵（Keys，不可變）與值（Values，可變）
 - 使用 Key 來尋找對應的 Value，以上述例子來說即為使用字尋找讀音
 - Key 跟 Value 可以是任何資料類別，也可以不用一樣
 - 字典是無序的（在 `collections` 這個 library 中有提供有序字典）
 - 若查找不存在的 key 則會報錯，可以使用 `in` 或 `dict.get()` 來檢查

```python=
mydict = dict()  # or mydict = {}
print("Here is an empty dictionary:", mydict)
# Add new pair in dictionary
mydict[1] = 'one'
mydict[2] = 'two'
mydict[3] = 'three'
print("Dictionary now looks like: ", mydict)
print("2 is corresponding to:", mydict[2]) # Access value
```
```
Output:
Here is an empty dictionary: {}
Dictionary now looks like: {1: 'one', 2: 'two', 3: 'three'}
2 is corresponding to: two
```

```python=
# Continued from last cell
print(mydict.keys())
print(mydict.values())
print(mydict.items())
print(5 in mydict)
print(mydict.get(5))
```
```
Output:
dict_keys([1, 2, 3])
dict_values(['one', 'two', 'three'])
dict_items([(1, 'one'), (2, 'two'), (3, 'three')])
False
None
```

#### 集合（Set）
 - 與數學中的集合概念類似，只能儲存唯一（Unique）元素，相同元素不會重複出現
 - 因為是無序，故我們不能使用 `set[0]` 的方式來取值
 - 可以使用 `set.add(item)` 與 `set.remove(item)` 來新增與刪除元素
 - 可以使用 `set(list)` 將 List 轉為 Set，藉此檢查清單中唯一元素個數
 - 相關操作有聯集、交集、差集等等

```python=
aset = {11, 22, 33}
bset = {33, 44, 55}
print("Union:", aset | bset)
print("Intersection:", aset & bset)
print("Difference(A-B):", aset - bset)
print("Difference(B-A):", bset - aset)
print("Symmetric difference:", aset ^ bset)
```
```
Output:
Union: {33, 22, 55, 11, 44}
Intersection: {33}
Difference(A-B): {11, 22}
Difference(B-A): {44, 55}
Symmetric difference: {11, 44, 22, 55}
```

![image](https://hackmd.io/_uploads/BkvMrFNM0.png)

> 補充：特別注意 [運算元優先順序](https://june.monster/python-101-operators-and-priority/)！

#### 統整
| 類別 | Tuple | List | Dict | Set |
| --- | --- | --- | --- | --- |
| 符號 | ( ) | [ ] | { } | { } |
| 可變性 | 不可變 | 可變 | 可變 | 可變 |
| 順序性 | 有序 | 有序 | 無序 | 無序 |


### 檔案讀取（File I/O）
在 Python 中，很常會用到檔案相關的操作，舉凡文字檔（.txt）、CSV檔（.csv）、圖片檔（.png, .jpg...）、影片檔（.mp4, .avi...）等等，都會需要讀取、寫入檔案。這邊先以文字檔作為示範，僅簡單講解基礎操作，其他檔案如圖片、影像有些會有專門的 library 來處理。

test.txt:
This is a test txt file.
This is another line.

 - 全部讀入
    ```python=
    file = open('test.txt','r')
    data = file.read()
    file.close()
    print(data)
    data = data.split('\n')
    print(data)
    ```

    ```
    Output:
    This is a test txt file.
    This is another line.
    ['This is a test txt file.', 'This is another line.']
    ```
 - 逐行讀入
    ```python=
    file = open('test.txt','r')
    while True:
        line = file.readline()
        if not line:
            break
        print(line,end='')
    file.close()
    ```
    ```
    Output:
    This is a test txt file.
    This is another line.
    ```

 - 寫入檔案
     - 新增在原始資料後面
    ```python=
    file = open('test.txt','a')
    file.write('This is a new line.')
    file.close()
    ```
    test.txt:
    This is a test txt file.
    This is another line.
    This is a new line.
    - 從頭重新寫入（會覆蓋原始資料）
    ```python=
    file = open('test.txt','w')
    file.write('This is a new line.')
    file.close()
    ```
    test.txt:
    This is a new line.

要記得加上 `file.close()` 來關閉檔案，以免造成潛在的 Memory Leak。有一個更好的寫法，使用 `with` 來達成，如下例：
```python=
with open('test.txt','r') as file:
    # Do some file-related operations
    # The file will close automatically when this block is finished
# Do other operations
```
將檔案相關操作放在 `with` 的區塊中，而非檔案相關操作放在外面，一方面能確保檔案有被關閉，一方面也能增加可讀性。

### 例外處理（Exception Handling）
寫程式難免會遇到 Error 的狀況，當我們不希望程式因為 Error 而停止執行並噴出一大堆錯誤訊息時，可以使用以下技巧來處理。
 - `try` 必須搭配 `except` ，預設先執行 `try` 裡的程式碼
 - 當 `try` 執行失敗時， `except` 裡才會被執行
 - 與 `if...else...` 有異曲同工之妙，但不會因遇到錯誤而停止執行
 - 有時候會造成難以 debug ，使用上要特別小心
 - 另外可以使用 `raise` 來定義自己想要的 Exception

```python=
x = input()
if not x.isdigit():
    raise Exception("Not A Integer")
else:
    x = int(x)
    
try:
    inv = 1/x
    print(inv)
except ZeroDivisionError:
    print('Denominator cannot be 0!')
except TypeError:
    print('Type is not correct!')
except:
    print('Other Error!')
```
```
Output (when input = 2): 0.5
Output (when input = 0): Denominator cannot be 0!
Output (when input = 'A'): ... Exception: Not A Integer
```
此處要注意的是，前兩種狀況程式可以順利結束，因為我們使用 `except` 來處理分母為0的例外；但第三種狀況 Python 會報錯，程式中斷無法繼續往下執行，因為我們 寫「當 x 不是數字時就 raise error」，Python raise error 後就會停止。

### 斷言 （Assertion）
Assertion 提供一種保護機制，確保執行到某個地方時，某樣我們預期的條件仍然成立。若不成立則會丟出 Assertion Error，可以加入自定義的訊息。

```python=
x = int(input())
assert x >= 0, 'x is not positive'
print('A Positive number is:',x)
```
```
Output (when input = 1): A Positive number is: 1
Output (when input = -1): ... AssertionError: x is not positive
```
### Lambda
Lambda 又叫做匿名函數，當我們需要快速簡潔的撰寫一個函數，但又不想幫他命名時（意即這個函數可能只會用一兩次），我們就會使用 Lambda 來幫助我們。Lambda 在使用上依然可以給予名稱，但非必要，函數內容也必須在一行內結束。
```python=
>>> print((lambda x : x ** 2)(10))
100
>>> print((lambda x, y: x * y)(4, 5))
20
>>> print((lambda x: x[1])([1,2,3]))
2
```

#### 與其他函數的搭配使用
 - filter()
    ```python=
    numbers = [1,10,100,1000,10000]
    bignums = filter((lambda x: x > 50), numbers)
    print(list(bignums))
    ```
    ```
    Output:
    [100,1000,10000]
    ```
 - map()
    ```python=
    numbers = [1,10,100,1000,10000]
    doublenums = map((lambda x: x * 2), numbers)
    print(list(doublenums))
    ```
    ```
    Output:
    [2, 20, 200, 2000, 20000]
    ```
 - sorted()
    ```python=
    food = [('Apple',10),('Coke',30),('Bread',5),('Candy',25)]
    food_sorted = sorted(food, key = lambda x: x[1])
    print(food_sorted)
    ```
    ```
    Output:
    [('Bread', 5), ('Apple', 10), ('Candy', 25), ('Coke', 30)]
    ```
> 參考 [Python Lambda 應用技巧](https://www.learncodewithmike.com/2019/12/python-lambda-functions.html)

### 套件（Library）
Python 強大的地方就是其眾多的使用者，讓我們在網路上有許多參考資料，以及眾多的第三方套件可供我們使用。套件其實就是別人寫好的 .py 檔案，將其整理後丟到網路上，讓我們可以透過一行簡單的 `import [package]` 就能使用。
 - 安裝套件：使用 `pip install [package]`
    有些套件如 `os`, `random`, `time` 等等已預先包含在 python 中，就不需再另外下載
 - 載入套件
     - 整個套件載入
         - `import [package]`（推薦）
         - `from [package] import *`
     - 僅載入特定模組/函數
         - `from [package] import [module/function]`（推薦）
         - `import [package].[module]`
     - 載入且化名
         - `import [package] as [name]`
 - 使用套件：多以`[package].[function]`的方式，若是僅載入特定模組/函數的話，前面不須加套件名稱即可使用。以下四種方式結果皆相同，但為了方便管理我們一般會選用第一種，以便知道各個函數來自哪個套件，同時也不會不小心覆寫（Overwrite）某些函數。
```python=
import os
print(os.getcwd())
```
```python=
from os import getcwd
print(getcwd())
```
```python=
import os as O
print(O.getcwd())
```
```python=
from os import getcwd as gw
print(gw())
```
> 進階：參考 [Python 的 import 陷阱](https://medium.com/pyladies-taiwan/python-%E7%9A%84-import-%E9%99%B7%E9%98%B1-3538e74f57e3)

#### 常用套件
 - GUI：tkinter
 - 遊戲設計：pygame
 - 數學運算：math, random, numpy, scipy, random
 - 資料處理：numpy, pandas
 - 視覺化：matplotlib, seaborn
 - 機器學習：scikit-learn, pytorch, tensorflow, keras
 - 網站建置：flask, django
 - 資料庫處理：pymysql
 - 影像處理：cv2, PIL
 - 自然語言處理：nltk, jieba
 - 電腦操作：os, sys
 - 時間相關：time, datetime
 - 網路爬蟲：request, beautifulsoup, selenium
> 參考 [Python 第三方模組](https://cflin.com/course/python/Python_07.pdf)

## Git 版本控制
Git 是一種版本控制系統，它可以追蹤軟體開發過程中的變更，幫助開發人員更有效地管理程式碼。使用 Git 有許多好處：

1. 版本控制：Git 可以幫助開發人員追蹤檔案的更改，並在需要時輕鬆地回復到先前的版本。這樣可以減少錯誤和失誤，並提高程式碼品質。
2. 合作開發：Git 可以讓多個開發人員協同工作，讓他們在同一時間在同一份程式碼上工作，並且避免不同人員之間的衝突。
3. 分支管理：Git 可以讓開發人員在不影響主分支的情況下創建和管理多個分支。這可以讓開發人員在不同的功能上工作，而不必擔心對主分支的影響。
4. 遠端存儲：Git 可以讓開發人員將代碼儲存在遠端儲存庫中，讓多個開發人員在不同地方協同工作。

Git 在許多著名的開源軟體專案中得到廣泛使用，包括Linux核心、Ruby on Rails 和 jQuery。使用 Git 的方式一般有兩種：使用指令（Command Line）或是下載 Github Desktop 使用其軟體介面（GUI），我們這邊會先介紹如何使用 Github Desktop。

Credit: The world-wide famous [ChatGPT](https://chat.openai.com/chat)

參考以下連結：
- [官方說明](https://docs.github.com/zh/desktop/installing-and-configuring-github-desktop/overview/getting-started-with-github-desktop)
- [從 0 到 1 的 GitHub Pages 教學手冊](/cW7RxOjzQ4eqQlZbOW9BsA)
- [Git 教學 - 為你自己學 Git](https://gitbook.tw/)

## Python 進階
### 物件導向程式設計（Object-Oriented Programming, OOP）
物件導向程式設計是軟體設計的一種方法，它把軟體分成數個「物件」來撰寫。每個物件都有自己的屬性和行為，並且可以跟其他物件互動。這樣的好處是，軟體的各部分之間彼此獨立，不但便於重複使用，也更容易理解和修改，提高軟體的可維護性和可擴展性。

物件導向程式設計是目前最流行的軟體設計方法之一，被廣泛應用於各種領域，包括網站開發、商用軟體、遊戲開發等等。常見的物件導向程式設計語言包括 Java、C++、C#、Python 等。

Credit: The world-wide famous [ChatGPT](https://chat.openai.com/chat)

### 類別（Class） - 簡介
以下我們使用一個簡單的例子來說明類別的概念：在現實生活中，有各式各樣的車子，而每台車子雖然皆不相同，但都具有共同特徵，像是有四個輪胎、都有駕駛與車牌跟廠牌、都使用汽油前進等等，這時候就很適合使用物件導向的概念為車子建造一個類別。

在以下的例子中，`Car` 是一個類別名稱，這個類別包含 `driver, engine, meter` 等等屬性（Attribute），以及 `turnOnEngine, checkEngine, drive` 等等方法（Method）。

而 `mycar` 是一個屬於 `Car` 類別的物件或變數，我們也可以建立多個屬於 `Car` 類別的物件像是 `mycar1, mycar2...`，彼此之間的屬性與函數操作互不影響。

#### 宣告類別與建構函式（Constructor）
在宣告類別時，我們使用以下語法：
- `class Car` 代表這個類別的名稱，亦可使用 `class Car()` 或 `class Car(object)`
- `def __init__()` 是一種特殊的類別方法，也稱為建構函式
    - 一個類別只有一個建構函式，若未撰寫則預設什麼事情都不做
    - 名稱必為 `__init__()`，建立此類別物件時會自動執行，不須呼叫
    - 主要用途為初始化相關配置，像是車子必有車牌號碼等等
```python=
class Car:  # or class Car(): / class Car(object):
    def __init__(self, plateID, driver):
        self.wheels = 4
        self.plateID = plateID
        self.driver = driver
        self.engine = False
        self.meters = 0
        self.turnOnEngine()
```

> 補充：在其他語言（如 C++）中，時常會見到解構函式（Destructor）的使用
> 與建構函式相對應，解構函式在物件被銷毀時會自動執行
> 其使用主要是為了刪除 Runtime 時動態分配的記憶體空間，以避免 Memory Leak
> Python 中也有提供解構函式，但因為我們通常不會自己分配記憶體
> 所以大多狀況下不需要使用，Python 會自己幫我們刪除分配的空間


#### 屬性（Attribute）與方法（Method）
- 屬性（Attribute）：靜態，描述此物件的屬性
    - 車子有駕駛、引擎、公里數等等
    - 又稱為成員變數（Member Variable）
    - 其值可以是任何東西，像是 `list`、`int`、`string` 等等，甚至可以是另一個類別
    - 會一直保存並且隨程式進行而更新，直到物件消滅為止
- 方法（Method）：動態，對此物件執行一個動作
    - 車子可以點燃引擎、檢查引擎、往前開等等
    - 又稱為成員函式（Member Function）
    - 與一般的函式（Function）撰寫方式相同
```python=
class Car:  # or class Car(): / class Car(object):
    def __init__(self, plateID, driver):
        self.wheels = 4
        self.plateID = plateID
        self.driver = driver
        self.engine = False
        self.meters = 0
        self.turnOnEngine()
        
    def turnOnEngine(self):
        if self.checkEngine():
            self.engine = True
            print("Engine Started!")
            
    def checkEngine(self):
        return True
    
    def drive(self, distance):
        if self.engine:
            self.meters += distance
            print("Drive %d kilometers."%distance)
        else:
            print('Engine is not turned on.')
    
    def turnOffEngine(self):
        self.engine = False
        print("Engine has been turned off.")
        
    def whoisDriving(self):
        print('%s is driving the car.'%self.driver)
        return self.driver

    def getMeters(self):
        return self.meters
```

#### Self
你應該有注意到上面出現了很多個 `self` 這個關鍵字，這個關鍵字在類別中扮演了很重要的角色，且任何類別方法中，第一個參數一定要是 `self`，他的意思是「這個物件本身」，而因為 `self` 代表這個方法中的物件本身，所以這個位置不需要傳入任何東西，在呼叫時可以直接無視。

用以下的例子來說：
```python=
class Car:
    ...
    def drive(self, distance):
        if self.engine:
            self.meters += distance
            print("Drive %d kilometers."%distance)
        else:
            print('Engine is not turned on.')

    def getMeters(self):
        return self.meters
```

```python=
...
print(myCar1.getMeters())
myCar1.drive(100)
print(myCar1.getMeters())
print(myCar2.getMeters())
print(myCar3.getMeters())
```

```
Output:
100
200
1000
0
```

可以注意到幾個重點：
 - 每輛車的結果都不同，因為每輛車的 `self.meters` 都不同
 - 呼叫 `mycar1.getMeters()` 時，不用傳入任何參數，但定義時卻必須定義一個參數 `self`，也就是說，類別方法的傳入參數量 + 1 = 定義參數量
 - 也可以在類別方法內來呼叫其他類別方法，像是 `self.turnOnEngine()` 

#### 靜態變數（Static Variable）
上述例子中，有些屬性是屬於整個類別共享的，像是 `self.wheels`，所有車子都有四個輪子。此時我們可以利用靜態變數，來宣告整個類別的屬性。詳細作法如下：

```python=
class Car:  # or class Car(): / class Car(object):
    wheels = 4
    def __init__(self, plateID, driver):
        self.plateID = plateID
        self.driver = driver
        self.engine = False
        self.meters = 0
        self.turnOnEngine()
    ...

```
| 變數/屬性 | 說明 | 例子 | 語法 |
| ------ | -------- | -------- | -------- |
| 實體變數 | 每個物件的屬性 | 每輛車有不同的駕駛 | mycar.driver |
| 類別變數 | 整個類別的屬性 | 所有車都有 4 個輪子 | Car.wheels |

#### 使用方式
在完成以上的宣告後，接著我們來看使用方式：
- 使用 `Car()` 來建立一個類別物件
- 使用 `myCar.drive()` 來呼叫類別方法
- 使用 `myCar.driver` 來獲取類別屬性
```python=
myCar = Car("ABC-0311","Jack")
print('=====')
myCar.drive(100)
print('=====')
driverName = myCar.driver
print(driverName, "is driving the car.")
```

```
Output:
Engine Started!
=====
Drive 100 kilometers.
=====
Jack is driving the car.
=====
```

> 補充：在其他語言中，為了更好的管理獲取權限
> 有時候會限制類別屬性或方法的取的與使用
> 此舉可以避免類別屬性被意外的修改，像 C++ 中 `private` 與 `protected` 的使用

#### 完整程式碼
```python=
class Car:  # or class Car(): / class Car(object):
    wheels = 4
    def __init__(self, plateID, driver):
        self.plateID = plateID
        self.driver = driver
        self.engine = False
        self.meters = 0
        self.turnOnEngine()
        
    def turnOnEngine(self):
        if self.checkEngine():
            self.engine = True
            print("Engine Started!")
            
    def checkEngine(self):
        return True
    
    def drive(self, distance):
        if self.engine:
            self.meters += distance
            print("Drive %d kilometers."%distance)
        else:
            print('Engine is not turned on.')
    
    def turnOffEngine(self):
        self.engine = False
        print("Engine has been turned off.")
        
    def whoisDriving(self):
        print('%s is driving the car.'%self.driver)
        return self.driver

    def getMeters(self):
        return self.meters

myCar = Car("ABC-0311","Jack")
print('=====')
myCar.drive(100)
print('=====')
driverName = myCar.whoisDriving()
print('=====')
myCar.turnOffEngine()
print('=====')
myCar.drive(100)
print('=====')
myCar.turnOnEngine()
print('=====')
myCar.drive(100)
print('=====')
meter = myCar.getMeters()
print("Meters:",meter)
```

```
Output:
Engine Started!
=====
Drive 100 kilometers.
=====
Jack is driving the car.
=====
Engine has been turned off.
=====
Engine is not turned on.
=====
Engine Started!
=====
Drive 100 kilometers.
=====
Meters: 200
```
### OOP 三大精隨 - 封裝、繼承、多型（補充）
#### 封裝（Encapsulation）
將物件的內部狀態和行為隱藏在物件內部，只公開必要的方法給外界使用。封裝可以保護物件免於外界的非法存取，並且讓物件更容易維護和修改。
```python=
class Animal:
    name = ''
    __private = '' # This cannot be accessed from the outside
    def __init__(self, name):
        self.name = name
        self.__private = '' # This cannot be accessed from the outside
```

#### 繼承（Inheritance）
子類別可以繼承父類別的屬性和方法，並且可以擴展或覆寫父類別的行為。繼承可以提高程式碼重複使用性，並且可以讓類別之間建立階層關係，方便對類別進行分類和管理。
```python=
class Animal:
    name = ''
    def __init__(self, name):
        self.name = name

    def walk(self):
        print('walking')

    def eat(self):
        print('eating')


class Dog(Animal):
    def __init__(self, name):
        super().__init__(name)


A = Dog('A')
A.walk()
A.eat()
print(A.name)
```

```
Output:
walking
eating
A
```

#### 多型（Polymorphism）
同樣的方法名稱可以在不同的類別中有不同的實現方式，這稱為多型。多型可以讓程式碼更加靈活，並且可以讓不同的物件對相同的方法有不同的行為。多型可以通過繼承和介面實現，是物件導向設計中非常重要的概念。
```python=
class Animal:
    name = ''
    def __init__(self, name):
        self.name = name

    def walk(self):
        print('walking')

    def eat(self):
        print('eating')

        
class Dog(Animal):
    def __init__(self, name):
        super().__init__(name)

    def walk(self):
        print('{0} is using foot to walk'.format(self.name))

    def eat(self):
        print('{0} is eating bone'.format(self.name))
        
        
class Duck(Animal):
    def __init__(self, name):
        super().__init__(name)

    def walk(self):
        print('{0} is using two feet to walk'.format(self.name))

    def eat(self):
        print('{0} is eating worm'.format(self.name))


A = Dog('A')
B = Duck('B')
A.eat()
B.eat()
```

```
Output:
A is eating bone
B is eating worm
```


> Code Source: [搞懂Python的OOP](https://ithelp.ithome.com.tw/articles/10200623)

## 小結
到這裡為止你已經學完絕大部分常用的 Python 語法了，簡單開發所需的語法基本上不太會超過本篇教學的範圍。然而，資訊工程的領域極其廣大，目前碰到的還僅止於皮毛，若有興趣可以繼續鑽研資料結構、演算法等等課題，也可以透過題目或專案來練習自己的 Coding 能力。另外，網路上有很多相關資訊或教學，透過網路自我學習、不斷成長，也是件很重要的事情，加油！