# Angular FormGroup

FormGroup 是 Angular 中 Reactive Forms (反應式表單) 的一部分，用於管理和組織多個 FormControl (表單控制項或表單元件) 的容器，讓開發人員能夠輕鬆建立、驗證和管理複雜的表單。

FormGroup 通常用於包含多個欄位的表單，例如：註冊或登入表單。

<br />

## FormGroup 的屬性

- controls

    controls 屬性是一個 JavaScript 物件，包含了這個 FormGroup 中的所有控制項。每個控制項都以鍵值對 (Key-Value Pair) 的形式儲存，鍵是控制項的名稱，值是相應的 FormControl、FormGroup 或 FormArray。這樣可以比較輕鬆的存取、操作和管理各種表單元素。

    ```
    const formGroup = new FormGroup({
        username: new FormControl(''),
        password: new FormControl(''),
    });

    console.log(formGroup.controls);   // {username: FormControl2, password: FormControl2}
    ```

    在這個範例中，建立了一個 FormGroup，其中包含兩個控制項：`username` 和 `password`。透過 controls 屬性，可以存取這些控制項並對其進行操作。

- value

    value 屬性返回一個物件，其中包含了所有控制項的當前值，表示了目前表單的狀態。

    ```
    const formGroup = new FormGroup({
        username: new FormControl('Charmy'),
        password: new FormControl('123'),
    });

    console.log(formGroup.value);   // {username: 'Charmy', password: '123'}
    ```

    在這個範例中，`formGroup.value` 返回包含 `username` 和 `password` 當前值的物件。

- valid & invalid

    valid 屬性是一個 boolean，表示整個表單的有效性。只有當 FormGroup 中的所有控制項都通過了驗證，valid 才會是 `true`。這可以檢查整個表單是否有效，不需要逐一檢查每個控制項。

    invalid 屬性與 valid 相反，當表單中有任何一個控制項無效時，會返回 `true`。invaild 適用於顯示錯誤訊息或防止用戶提交無效表單。
    
    ```
    const formGroup = new FormGroup({
        username: new FormControl('Charmy', Validators.required),
        password: new FormControl('', Validators.required),
    });

    console.log(formGroup.valid);   // false
    console.log(formGroup.invalid);   // true
    ```

    在這個範例中，為 `username` 和 `password` 添加 `Validators.required` 驗證器。因為 `password` 欄位是空的，所以 `formGroup.valid` 返回 `false`，而 `formGroup.invalid` 則返回 `true`。
