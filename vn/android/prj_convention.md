### Tham chiếu từ: 

[Framgia_convention](https://github.com/framgia/coding-standards/blob/master/vn/android/codingstyleguide.md)

Tuy nhiên trong đấy có 1 số quy định chung chung (vd: có thể dùng cách 1 hoặc cách 2...) hoặc chưa đề cập đến 

-> muốn định nghĩa thêm để cả nhà cùng thống nhất cho đơn giản -> chỉ dùng 1 cách.
### Bổ sung:

~~Trong một số trường hợp ___không sử dụng ngoặc kép___~~ 

~~`if (condition) body`();~~

--> luôn sử dụng ngoặc {...} dù chỉ 1 line code

```java
if (condition) {
 body();
}
```

### 3.2 Đặt tên resources

Resource IDs và tên cần khai báo theo lowercase_underscore

#### 3.2.1 Đặt tên ID

Các ID nên bắt đầu bằng tên phần tử và chữ thường gạch chân. Thêm ý nghĩa của view (vd: `@+id/text_name`)

Ví dụ:

| Element              | ID Prefix              |
| -----------------    | -----------------   |
| `TextView`           | `text_`   (không đặt txt_ hoặc text_view_          |
| `EditText`           | `input_`  (vd: input_password)          |
| `ImageView`          | `image_`  (vd: image_avatar)          | 
| `Button`             | `button_` (vd: button_login)          |   
| `Menu`               | `menu_`             |
| `RelativeLayout`     | `layout_`         |
| `LinearLayout `      | `layout_`           |
| `CheckBox `          | `check_`            |
| `RecyclerView `      | `list_`             |
| `ListView `          | `list_`            |

#### 3.2.2 Strings

~~Tên chuối bắt đầu bằng một định danh. Ví dụ `registration_email_hint` hoặc `registration_name_hint`. 
Hoặc nếu không thì theo quy luật sau:~~ --> đặt tên theo nội dung của text

| Element              | ID                  |
| -----------------    | -----------------   |
| `hello`              | `hello`             |
| `How are you?`       | `how_are_you`       | 
| `Registration`       | `registration`      |   
| `This is a very long paragraph and you can not put text too long here`               | `this_is_a_very_long_paragaph`  |

#### 3.2.4 Colors

Color khai báo theo màu. vd: `<color name="redLight">#FAA</color>`

| Hex    | Id         |
| ------ | ---------- |
| #FAA   | redLight  |
| #F22   | redDark   |
| #FFF   | white      |

#### 3.2.5 Dimens

Dimens khai báo theo format:

| Prefix       | Ý nghĩa    |
| ------------ | ---------- |
| text_size_   | text size (sp)  |
| line_height_   | line height (sp)  |
| padding_   | paddingLeft, right...  |
| margin_   | margin left, right...  |
| icon_   | icon size (icon nhỏ, vd: icon action bar, toolbar...  |
| image_   | image size (vd: avatar, image, background)  |
| height_   | view/layout height  |
| width_   | view/layout width  |
| size_   | other sizes (shadow, border, elevation,...)  |

các loại dimens:

| Prefix       | Ý nghĩa    |
| ------------ | ---------- |
| negative_   | số âm (<0)  |
| nano_   | size rất rất nhỏ  |
| tiny_   | size rất nhỏ  |
| micro_   | size nhỏ  |
| small_   | size nhỏ  |
| default_   | mặc định  |
| normal_   | bình thường  |
| large_   | lớn  |
| huge_   | rất lớn  |

kết hợp nhiều thuộc tính: vd: `margin_default_extra`, `margin_negative_tiny`, `text_size_xxxxlarge`

các thuộc tính mặc định nên là bội số của 8 (material design). Các dimen bổ sung sẽ được đánh số:

| Prefix       | Value    |
| ------------ | ---------- |
| margin_default    | 16dp  |
| margin_default1   | 18dp  |
| margin_normal   | 24dp  |
| margin_normal1   | 24.5dp  |
| margin_large   | 48dp  |
| margin_large1   | 49dp  |
| margin_large2   | 49.5dp  |
| margin_large3   | 51dp  |

#### 3.2.6 Drawable 

Đặt tên icon với prefix là tên màn hình:

| icon       | ý nghĩa |
| ---------- | -------- |
| a1c_bg_a.png  | màn hình A-1c, ảnh thứ a |
| c2d_ic_homework8.png | màn hình C-2d, icon homework thứ 8 |
| e1_ic_action_notify.png | màn hình E-1, icon notify ở action bar |

*prefix là tên màn hình thường không đúng với các convention khác nhưng thuận tiện cho việc so sánh với design.*

### 3.3 Xử lý exception

Không throw RuntimeException trong code. nên in ra Log hoặc set default value. Như thế sẽ gây crash app.
