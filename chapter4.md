# 四、格式化建議





## 術語說明

區塊化結構是指一個類別、方法或建構子的本體。而後面將會提到，一個陣列的初始化樣式也可視為是種區塊化結構。

#### **4.1 括號(Braces)**

>4.1.1 即使不是必要的大括號，仍應加上(Braces are used where optional)

在使用```if, else, for, do ```和 ```while``` 等程式敘述時都必須加上大括號，即使方法本體可能是空白的或是內容只有單行。

>4.1.2 不是空白的區塊： 使用K &R 風格(Nonempty blocks: K & R style)

本體不是空的大括號或是由大括號所組成的結構，應遵守Kernighan and Ritchie style原則：

1. 在起使大括號前不應換行
1. 在起始大括號後進行換行
1. 在結束大括號前應換行
1. 若是結束大括號意味著一段程式敘述的終點，像是方法本體、建構子本體、Class本體，其後必須換行。相對的、像是else敘述或逗號後即可不換行。

例如：

    return new MyClass() {

      @Override public void method() {
  
        if (condition()) {
          try {
            something();
          } catch (ProblemException e) {
            recover();
          }
        }
      }

    };

但有些例外狀況，像是Enum類別的運用，這部分將在後面提到。

>4.1.3 空的區塊： 讓他簡潔一些(Empty blocks: may be concise)

