# Coding convention Android

## 1. Quy tắc đặt tên file

### 1.1 Đặt tên lớp
* Tên lớp viết dạng [UpperCamelCase](http://en.wikipedia.org/wiki/CamelCase). (Là danh từ, và viết hoa tất cả các chữ cái đầu,...).
* Nếu lớp mà được extend từ một lớp thành phần của Android thì tên lớp phải được kết thúc bằng tên của lớp thành phần này. Ví dụ: `SignInActivity`, `SignInFragment`, `ImageUploaderService`, `ChangePasswordDialog`.

### 1.2 Đặt tên Resource files
Cấu trúc chung viết theo dạng __lowercase_underscore__ (viết thường, phân cách bởi dấu gạch dưới)

#### 1.2.1 Drawable files
| Asset Type   | Prefix            |		Example               |
|--------------| ------------------|-----------------------------|
| Action bar   | ab_             | ab_stacked.9.png          |
| Button       | btn_	            | btn_send_pressed.9.png    |
| Dialog       | dialog_         | dialog_top.9.png          |
| Divider      | divider_        | divider_horizontal.9.png  |
| Icon         | ic_	            | ic_star.png               |
| Menu         | menu_	           | menu_submenu_bg.9.png     |
| Notification | notification_	| notification_bg.9.png     |
| Tabs         | tab_            | tab_pressed.9.png         |

Nếu drawable thuộc loại selector thì trạng thái selector sẽ được đặt cùng hậu tố như sau

| State	       | Suffix          | Example                     |
|--------------|-----------------|-----------------------------|
| Normal       | `_normal`       | `btn_order_normal.9.png`    |
| Pressed      | `_pressed`      | `btn_order_pressed.9.png`   |
| Focused      | `_focused`      | `btn_order_focused.9.png`   |
| Disabled     | `_disabled`     | `btn_order_disabled.9.png`  |
| Selected     | `_selected`     | `btn_order_selected.9.png`  |

#### 1.2.2 Layout files
Tên của Layout nên bắt đầu bằng tên của Android components sẽ sử dụng nó, theo sau là tên của class sẽ sử dụng nó. 
Lưu ý: 
* Nếu Layout được sử dụng như là một phần của `Adapter` hoặc `ListView` thì tên Layout sẽ bắt đầu bằng `item_`. 
* Nếu Layout là một phần của Layout khác thì tên sẽ được bắt đầu bằng `partial_`.

Ví dụ:

| Component        | Class Name             | Layout Name                   |
| ---------------- | ---------------------- | ----------------------------- |
| Activity         | `UserProfileActivity`  | `activity_user_profile.xml`   |
| Fragment         | `SignUpFragment`       | `fragment_sign_up.xml`        |
| Dialog           | `ChangePasswordDialog` | `dialog_change_password.xml`  |
| AdapterView item | ---                    | `item_person.xml`             |

#### 1.2.3 Menu files

Tên của menu file được đặt tương tự như Layout file: Bắt đầu bằng tên của Android component sẽ sử dụng nó và theo sau là, theo sau là tên của class sẽ sử dụng nó. Lưu ý là không đính kèm từ `menu` vào phần tên vì mặc định những file này đã nằm trong thư mục menu.
Ví dụ tên lớp `UserActivity` thì menu file sẽ được đặt là `activity_user.xml`. 

## 2. Quy tắc đặt tên trong code

### 2.1 Đặt tên biến

Việc định nghĩa các biến luôn được đặt ở __đầu file__ và theo các quy tắc sau:
* Biến private, non-static tên bắt đầu bằng __m__
* Biến private, static tên bắt đầu bằng __s__
* Các biến khác viết thường chữ cái đầu, các từ tiếp theo viết hoa chữ cái đầu
* Biến là hằng thì viết hoa toàn bộ và phân cách bằng dấu gạch dưới
* Những từ viết tắt thì tất cả các chữ cái của từ đó phải viết hoa

Ví dụ:

```java
public class MyClass {
    public static final int SOME_CONSTANT = 42;
    public int publicField;
    private static MyClass sSingleton;
    int mPackagePrivate;
    private int mPrivate;
    protected int mProtected;
}
```

| Good           | Bad            |
| -------------- | -------------- |
| `XmlHttpRequest` | `XMLHTTPRequest` |
| `getCustomerId`  | `getCustomerID`  |
| `String url`     | `String URL`     |
| `long id`        | `long ID`        |



