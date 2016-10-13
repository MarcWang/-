
# 介面測試(UI Testing)
# 單元測試(Unit Testing)
# 整合測試(Integration Testing)



# Test-driven development(TDD)


### 單元測試(UNIT TESTING)撰寫注意事項
- 測試程式碼不應接觸任何外部資源(External Resources)

- 一個測試案例只測一種方法
- 最小的測試單位
- 不與外部（包括檔案、資料庫、網路、服務、物件、類別）直接相依
不具備邏輯
- 測試案例之間相依性為零


### 整合測試(INTEGRATION TESTING)
- 針對專案的一部分或全部進行測試

### 測試驅動開發(TEST-DRIVEN DEVELOPMENT)
- 以測試來驅動軟體開發


## What is a Unit Test?
- 單元測試是額外撰寫程式碼，測試最小單位的所有可能狀況，以確保此代碼完全沒有問題。

- 一般程式設計都會撰寫`Class`或`Object`，而`Class`不外乎會包含變數(variable)及函數(function)，其包含建構式(constructor)、方法(methods)及屬性(property)。

#### Code Coverage

#### Cyclomatic Complexity 循環複雜度

- 如果需要撰寫20個測試才能完成一個100%函數單元測試，那代表循環複雜度過高，必須重新設計該函數。

#### Parameter Value Coverage(PVC)

- 確保預期和非預期的參數傳入

#### 開放封閉原則（Open Close Principle, OCP）

#### 控制反轉 ( Inversion of Control, IoC )
- 這個把初始化動作，由原本目標物件內，轉移到目標物件之外，稱作「控制反轉」，也就是 IoC。

#### 依賴注入 DI
- 這個把依賴的物件，透過目標物件公開建構式，交給外部來決定，稱作「依賴注入」，也就是 DI。

#### Repository Pattern
- 讓使用端無須瞭解目標物件的相依關係

#### Legacy Code


```cs
public bool CompareStrings(String inStr1, String inStr2)
{
    return inStr1.Equals(inStr2);
}
```

應該測試
- An actual string: “SomeText”;
- An uninitialized string: null;
- A blank string: “”
- A string with only whitespace: ”   “;

```cs
public bool CompareStrings_Test()
{
    String test1 = null;
    String test2 = null;
    bool expected = false;
    bool actual = CompareStrings(test1, test2);
    Assert.AreEqual(expected, actual);
}
```

System.Int32 System.String
- A positive integer
- A negative integer
- Zero
- int.MaxValue or 2,147,483,647
- int.MinValue or -2,147,483,648

System.String
- A null string
- An empty string, String.Empty, or “”
- One or more spaces ” “
- One or more tabs ” “
- A new line or Environment.NewLine
- A valid string.
- An invalid or junk string
- Unicode characters such as Chinese

```cs
[TestClass()]
public sealed class DivideClassTest
{
    [ClassInitialize()]
    public static void ClassInit(TestContext context)
    {
        MessageBox.Show("ClassInit " + context.TestName);
    }

    [TestInitialize()]
    public void Initialize()
    {
        MessageBox.Show("TestMethodInit");
    }

    [TestCleanup()]
    public void Cleanup()
    {
        MessageBox.Show("TestMethodCleanup");
    }

    [ClassCleanup()]
    public static void ClassCleanup()
    {
        MessageBox.Show("ClassCleanup");
    }

    [TestMethod()]
    public void DivideMethodTest()
    {
        DivideClass.DivideMethod(0);
    }
}
```
