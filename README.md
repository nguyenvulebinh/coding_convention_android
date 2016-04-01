# Coding convention Android

## 1. Quy tắc đặt tên file

### 1.1 Đặt tên lớp
* Tên lớp viết dạng [UpperCamelCase](http://en.wikipedia.org/wiki/CamelCase). (Là danh từ, và viết hoa tất cả các chữ cái đầu,...).
* Nếu lớp mà được extend từ một lớp thành phần của Android thì tên lớp phải được kết thúc bằng tên của lớp thành phần này. Ví dụ: `SignInActivity`, `SignInFragment`, `ImageUploaderService`, `ChangePasswordDialog`.

### 1.2 Đặt tên Resource files
Cấu trúc chung viết theo dạng __lowercase_underscore__ (viết thường, phân cách bởi dấu gạch dưới)

####1.2.1 Drawable files
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


