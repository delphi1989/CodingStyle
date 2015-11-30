# 命名方式

#### **5.1 識別字串通用的規則**

識別字（物件參考）只利用ASCII字元及數字來表示，或如下所舉的例子，使用底線。因此每個有效的識別字都能在正則表達式中以```\w+``` 去配對

在Google Style中，特別的前綴或後綴，像是在下面的例子中：

```name_ , mName , s_name and kName```皆不使用

#### **5.2 不同類型的識別字串規則**

>5.2.1 Package命名

package的名稱皆由小寫字母構成，由不同的單字串接起來（不使用底線）。例如：```com.example.deepspace```是正確的，
而不使用 ```com.example.deepSpace``` 或 ```com.example.deep_space```

>5.2.2 類別命名

類別名稱以**大寫駝峰式字型**（**UpperCamelCase**）組成。
類別名稱多半為單純的名詞或是名詞片語，例如：Character 或 ImmutableList。介面的命名方式亦相同（如List），但有時會以形容詞或形容詞片語代替（如：Readable）

對Annotation型別而言，並沒有特定或是固有的規則去命名。

測試類別以將要被測試的類別名稱作為開頭，而以**Test**單字作結，例如：HashTest、HashIntegrationTest

>5.2.3 方法命名

方法名稱以**小寫駝峰式字型**（**LowerCamelCase**）組成。
方法的名稱通常是動詞或是動詞片語，例如：sendMessage 或 stop。

底線可能會出現在Junit的Test方法中，用來分隔方法名稱的邏輯組合。典型的格式是：
test<要被測試的方法>_<狀態>，例如testPop_emptyStack。對於test方法並沒有明確的定義如何命名。

>5.2.4 常數命名

常數的名稱以全部大寫字母的方式，並以底線分割單字，像是CONSTANT_CASE。但常數究竟是什麼？

每個常數都是```static final```屬性，但不是每個```static final```屬性都是常數。在決定使用常數式命名前（全部使用大寫字母），應思考究竟該項屬性是否真的是個常數。例如，當一個實例（Instance）中可被存取的狀態（屬性）是可變的，幾乎可以確定該狀態不是個常數。若認為單純的不去改變物件即可，這樣的條件是不夠的。例如：

    // Constants
    static final int NUMBER = 5;
    static final ImmutableList<String> NAMES = ImmutableList.of("Ed", "Ann);
    static final Joiner COMMA_JOINER = Joiner.on(','); // because Joiner is immutable
    static final SomeMutableType[] EMPTY_ARRAY = {};
    enum SomeEnum { ENUM_CONSTANT }

    // Not constants
    static String nonFinal = "non-final";
    final String nonStatic = "non-static";
    static final Set<String> mutableCollection = new HashSet<String>();
    static final ImmutableSet<SomeMutableType> mutableElements = ImmutableSet.of(mutable);
    static final Logger logger = Logger.getLogger(MyClass.getName());
    static final String[] nonEmptyArray = {"these", "can", "change"};

這些名稱通常是以典型的名詞或名詞片語式命名

>5.2.5 非常數屬性命名

非常數的屬性名稱（如static或其他的）是以**小寫駝峰式字型命**名（**LowerCamelCase**）這些名稱通常都是名詞或名詞片語，例如： ```computerValue``` 或 ```index```

>5.2.6 參數命名

參數名稱是以**小寫駝峰式字型**命名（**LowerCamelCase**）。
應避免只有單一字元的參數名稱

>5.2.7 區域變數命名

區域變數的命名也是以**小寫駝峰式字型**命名（**LowerCamelCase**），且相較於其他的型別可以有彈性的縮短
儘管如此，單一字元的命名仍應避免，除了那些暫時取用的得區域變數，或是用在迴圈內的變數。

即使是在 ```final```或是immutable的情況下，區域變數也並不被認為是個常數，因此也不應該以常數式方式（全部使用大寫字母）命名

>5.2.8 類別變數命名

每個型別變數（例如佔位符號T）只會以一兩種風格命名：
1. 一個大寫的字母，其後可能有一個數字（例如：E、T、X、T2）
2. 以類別的格式命名，並由一個大寫字母結束（例如：RequestT、FooBarT）


#### **5.3 駝峰式命名**

有時候，你有許多理由，使你將英文片段轉換成駝峰式字母的格式，例如當命名採取縮寫或是使用較不同的單字結構呈現時：```IPv6```、```iOS```。Google Style預先提供了以下幾項轉換的原則：

從散文形式(prose form)的名稱開始

1. 將整個名稱片段轉換成純ASCII的格式，並且移除撇號 ( ```' or ’```)。例如：
```Müller's algorithm```  轉換```成Muellers algorithm```。
1. 將上面的結果分割成單字（word），當遇到空白或其他標點符號時也進行拆分（通常是連字號 ```-``` ）。

      建議：如果有單字平常在使用時就已使用了駝峰式字型來呈現，也將它拆分成組成該名稱片段的單字，例（```AdWords``` 可以轉變成```ad words```）。但請留意，像是```iOS```這樣的單字，它在本質上並不屬於駝峰式的字型，它違反了其他的慣例，因此這個建議不適用在這樣的單字上。

1. 
將每個字母都轉成小寫的字母（包含縮寫），接著將配合下列的情況，把第一個字元轉為大寫字母：
  1. 每一個單字，建立大寫式駝峰
  1. 除了第一個以外的單字，建立小寫式駝峰
1. 
最後，將每個單字合併成單一的識別字

**注意**：原本單字的字母大小寫可以說是完全忽視了，例如：

    XML HTTP request   -> XmlHttpRequest  (O)  -> XMLHTTPREQUEST (X)
    new  customer ID   -> newCustomerId (O) -> newCustomerID(X)
    inner stopwatch   -> innerStopwatch (O) -> innerStopWatch(X)
    supports IPv6 on iOS   -> supportsIpv6OnIos(O) -> supportsIPv6OnIOS(X)
    YouTube Importer   -> YouTubeImporter(O) -> YoutubeImporter (O)*

***是可被接受的，但不建議這樣做**

**留意**：在英文中，有些單字因可利用連字號(```-```)使用而使它的字面形式具有模糊性，例如： ```nonempty``` 以及 ```non-empty``` 都是正確的，因此方法的名稱如： ‘checkNonempty’ 和 ‘checkNonEmpty’同樣的也都是正確的。



