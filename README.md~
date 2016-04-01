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

## 2. Quy tắc trong code

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


Có các thành phần trong Android sử dụng các cặp Key-value như `SharedPreferences`, `Bundle`, hay `Intent`. Khi sử dụng những thành phần này các Key phải được định nghĩa là các hằng số dạng `static final` và tên được bắt đầu như sau:

| Element            | Field Name Prefix |
| -----------------  | ----------------- |
| SharedPreferences  | `PREF_`             |
| Bundle             | `BUNDLE_`           |
| Fragment Arguments | `ARGUMENT_`         |
| Intent Extra       | `EXTRA_`            |
| Intent Action      | `ACTION_`           |

Ví dụ:

```java
// Note the value of the field is the same as the name to avoid duplication issues
static final String PREF_EMAIL = "PREF_EMAIL";
static final String BUNDLE_AGE = "BUNDLE_AGE";
static final String ARGUMENT_USER_ID = "ARGUMENT_USER_ID";

// Intent-related items use full package name as value
static final String EXTRA_SURNAME = "com.myapp.extras.EXTRA_SURNAME";
static final String ACTION_OPEN_USER = "com.myapp.action.ACTION_OPEN_USER";
```

### 2.2 Đặt Log

Lấy tên lớp làm giá trị cho Tag trong hàm ghi Log. Tag thường là hằng và được định nghĩa ở đầu lớp.

Các loại log như VERBOSE hay DEBUG chỉ được sử dụng trong bản debug, trong bản release sẽ phải loại bỏ

Ví dụ: 

```java
public class MyClass {
    private static final String TAG = MyClass.class.getSimpleName();

    public myMethod() {
        Log.e(TAG, "My error message");
	if (BuildConfig.DEBUG) Log.d(TAG, "mesage");
    }
}
```

### 2.3 Thứ tự đặt tham số trong phương thức

Trong các phương thức biến `Context`(nếu có) thì luôn đặt ở đầu trong danh sách tham số, ngược lại các biến `callback`(nếu có) luôn đặt ở cuối

Ví dụ:

```java
// Context always goes first
public User loadUser(Context context, int userId);

// Callbacks always go last
public void loadUserAsync(Context context, int userId, UserCallback callback);
```

### 2.4 Giới hạn độ dài trên một dòng

Một dòng không nên dài quá __100 ký tự__. Nếu một dòng mà dài hơn giới hạn này thì có 2 cách để giảm số ký tự xuống:
* Extract a local variable or method (preferable).
* Chia 1 dòng thành nhiều dòng

Ví dụ:

```java
int longName = anotherVeryLongVariable + anEvenLongerOne - thisRidiculousLongOne
        + theFinalOne;

Picasso.with(context)
        .load("http://ribot.co.uk/images/sexyjoe.jpg")
        .into(imageView);

loadPicture(context,
        "http://ribot.co.uk/images/sexyjoe.jpg",
        mImageViewProfilePicture,
        clickListener,
        "Title of the picture");
```

