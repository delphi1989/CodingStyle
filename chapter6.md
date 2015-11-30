# 設計實作建議

#### **6.1 總是使用@Override宣告**

無論何時，當使用```@Override```標記的方法是合法時則必須使用。像是子類別覆寫了父類別的方法，實作介面的類別覆寫了該介面的方法，子介面的方法重新指定父介面的方法

例外：```@Override``` Annotation 可能因要被覆寫的父方法已被宣告為```@Deprecated```而被省略

#### **6.2 捕捉例外： 不得忽視**

除了待會兒提到情況之外，不對捕捉到的例外進行任何處理，只有在特別的情境下是正確的。（一般而言都是對該例外進行Log，但若是該例外被認為不可能發生時，重新將該錯誤封裝為 ```AssertionError``` 後拋出）

當認為不對例外在 ```catch``` 區塊內進行任何處理是適當的行為時，應有註解針對這樣的決定進行合理的解釋，例如： 

    try {
      int i = Integer.parseInt(response);
      return handleNumericResponse(i);
    } catch (NumberFormatException ok) {
      // it's not numeric; that's fine, just continue
    }
    
    return handleTextResponse(response);
    
例外：在測試中，若一個被捕抓到的例外被命名為 expect （表示預期這個例外會產生）時，該例外有可能沒有任何註解解釋就被忽略。下面利用一常見的方式確保某方法在測試的情境下，會拋出預期型別的例外，因此無須有註解說明：    