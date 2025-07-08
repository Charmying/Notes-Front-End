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
