在 Swift 中，可选变量（Optional）是一种用于处理 值缺失 的类型。它允许变量既能存储某个值，也能存储 nil（表示没有值）。Swift 通过 ? 和 ! 来标记可选变量，以下是常见的使用方式：

1. 声明可选变量
    ~~~swift
    var name: String?  // 可能存储字符串，也可能是 nil
    name = "Swift"
    print(name)  // 输出 Optional("Swift")
    ~~~
2. 强制解包（Forced Unwrapping）
    ```swift
    var age: Int? = 25
    print(age!)  // 使用 `!` 取出值，确保它不为 nil
    ```
    ⚠️ 强制解包存在风险，如果 age 为 nil，程序会崩溃。
3. 可选绑定（Optional Binding）

    使用 if let 或 guard let 安全地解包：
    ```swift
    if let unwrappedAge = age {
        print("年龄是 \(unwrappedAge)")
    } else {
        print("年龄未知")
    }
    ```
4. 可选链（Optional Chaining）

    用于安全访问可能为 nil 的属性：

    ```swift
    class Person {
        var pet: String?
    }
    let person = Person()
    print(person.pet?.count)  // 如果 pet 为 nil，则不执行 '.count'
    ```
5. nil 合并运算符（Nil-Coalescing Operator）

    用于提供默认值：

    ```swift
    var nickname: String? = nil
    print(nickname ?? "默认昵称")  // 如果 nickname 为 nil，则使用 "默认昵称"
    ```