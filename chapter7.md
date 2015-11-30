# Javadoc




#### ** 7.1 格式化**

>7.1.1 通用格式

Javadoc區塊的基本格式化樣式如下：

    /** 
     * Multiple lines of Javadoc text are written here,
     * wrapped normally... 
     */
     public int method(String p1) { ... }

或是像這個單行格式化樣式的例子：

    /** An especially short bit of Javadoc. */
    
基本格式化樣式是通用的。當沒有使用Javadoc區塊、及Javadoc區塊（包含註解符號）可以使用單行就完成敘述時，單行格式化樣式可替代基本格式化樣式。  

>7.1.2 段落

在段落間或是在Javadoc標記群組之前，會有一行空行，該空行只有一個星號，沒有其他內容。除了第一個段落以外，每個段落在第一個字之前都會有```<p>```標籤，且第一字與```<p>```間沒有空白分隔

>7.1.3 @Javadoc標記

任一被使用的Javadoc標記會依照```@param、@return、@throws、@decrepated```的順序呈現，而這四個標記呈現時不會有空敘述的情況發生。當標記敘述超過一行時，接下來的敘述應相對於```@```符號(at-clause)有4個以上的空白縮排。


#### **7.2 摘要敘述**

給每個類別或是成員的Javadoc會以簡短的總結片段做為開始。這段簡短的總結片段非常的重要，因為在某些情境下、像是類別及方法索引中，是唯一呈現出來的文本。

**This is a fragment** -    fragment是名詞或動詞短語，不是完整的句子。他並非是以
 **A {```@code Foo```} is a …** 或 **This method returns …** 做為敘述的開始，也不是以一個完整的祈使句敘述開始，如 **Save the record** 。總結片段因首字大寫以及標點符號的影響而看起來像是個完整的句子。
 
 **tip**：在敘述簡單的Javadoc時，常見的錯誤是以 ```/** @return the cutstomer ID */```的形式撰寫，應該被改變為 ```/** Returns the customer ID. */```
 
 #### **7.3 該在何處使用Javadoc**
 
 至少，每個 ```public``` 類別，以及該類別內每個 ```public``` 或```protected``` 成員都應該擁有Javadoc。待會將會敘述一些例外。
其他的類別及成員視需求亦得有Javadoc。當一段註解將會是用來描述關於類別、方法或屬性的整體行為及目的時，那麼這段註解應被改寫為Javadoc替代（統一了規格，也使工具方便操作）