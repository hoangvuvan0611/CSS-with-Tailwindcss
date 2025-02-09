# CSS-with-Tailwindcss
Project mô tả các trường css của taiwind

## Layout

### aspect-ratio: Kiểm soát tỷ lệ khung hình của một thẻ
Các giá trị áp dụng:
- square(hình vuông - dùng cho thẻ img, ...): aspect-1/1 (hoặc tỷ lệ tương ứng cho hình bất kỳ)
- video(dùng cho thẻ iframe để nhúng video,...): aspect-video (hoặc có thể cấu hình
tùy ý theo giá trị với cú pháp chung `aspect-[value]` vd: "aspect-[calc(4*3+1)/3]")
...
### columns: kiểm soát columns trong một phần tử
```
- Cấu hình số lượng columns
columns-<number>                                        vd: columns-3 (có 3 columns trong thẻ);
- Cấu hình theo chiều rộng của columns
columns-3xs                                             vd: columns: var(--container-3xs); /* 16rem (256px) */ (Chiều rộng của cột)
columns-2xs                                             vd: columns: var(--container-2xs); /* 18rem (288px) */
columns-xs                                              vd: columns: var(--container-xs); /* 20rem (320px) */
columns-sm                                              vd: columns: var(--container-sm); /* 24rem (384px) */
columns-md                                              vd: columns: var(--container-md); /* 28rem (448px) */
columns-lg                                              vd: columns: var(--container-lg); /* 32rem (512px) */
columns-xl                                              vd: columns: var(--container-xl); /* 36rem (576px) */
columns-2xl                                             vd: columns: var(--container-2xl); /* 42rem (672px) */
columns-3xl                                             vd: columns: var(--container-3xl); /* 48rem (768px) */
columns-4xl                                             vd: columns: var(--container-4xl); /* 56rem (896px) */
columns-5xl                                             vd: columns: var(--container-5xl); /* 64rem (1024px) */
columns-6xl                                             vd: columns: var(--container-6xl); /* 72rem (1152px) */
columns-7xl                                             vd: columns: var(--container-7xl); /* 80rem (1280px) */
columns-auto                                            vd: columns: auto; (Xét theo giá trị tự động)
columns-(<custom-property>)                             vd: columns: var(<custom-property>);  (Xét theo giá trị cấu hình)
columns-[<value>]                                       vd: columns: <value>;
```
-> Sử dụng '--container-*' để cấu hình chiều rộng cố định của columns
vd: 
```
@theme {
  --container-4xs: 14rem; 
}
```
### break-after: xử lý việc ngắt dòng, cột hoặc trang ngay sau thẻ sử dụng css này (vd: một thẻ parent có 2 column và có nhiều phần tử con là các thẻ dev, thông thường các thẻ div sẽ được chia đều cho 2 column nhưng nếu sử dụng thẻ này thì nó sẽ ngắt column chứa nó và các thẻ div con còn lại mặc định sẽ được đưa hết vào column còn lại)
```
break-after-auto	              Giá trị mặc định, để trình duyệt tự quyết định ngắt hay không.
break-after-avoid	              Tránh ngắt sau phần tử.
break-after-all	                Luôn ngắt sau phần tử (nếu có thể).
break-after-avoid-page	        Tránh ngắt trang sau phần tử.
break-after-page	              Ngắt trang sau phần tử.
break-after-left	              Ngắt trang và để trang tiếp theo bắt đầu từ trang trái.
break-after-right	              Ngắt trang và để trang tiếp theo bắt đầu từ trang phải.
break-after-column	            Ngắt cột sau phần tử (trong layout nhiều cột).
```
### break-before: xử lý việc ngắt dòng, cột hoặc trang ngay sau thẻ sử dụng css này (vd: một thẻ parent có 2 column và có nhiều phần tử con là các thẻ dev, thông thường các thẻ div sẽ được chia đều cho 2 column nhưng nếu sử dụng thẻ này thì nó sẽ ngắt column chứa nó và các thẻ div con còn lại mặc định sẽ được đưa hết vào column còn lại)
```
break-before-auto	                Giá trị mặc định, để trình duyệt tự quyết định ngắt hay không.
break-before-avoid	              Tránh ngắt trước phần tử.
break-before-all	                Luôn ngắt trước phần tử (nếu có thể).
break-before-avoid-page	          Tránh ngắt trang trước phần tử.
break-before-page	                Ngắt trang trước phần tử.
break-before-left	                Ngắt trang trước và để trang tiếp theo bắt đầu từ trang trái.
break-before-right	              Ngắt trang và để trang tiếp theo bắt đầu từ trang phải.
break-before-column	              Ngắt cột trước phần tử (trong layout nhiều cột).
```
### break-inside: kiểm soát phần tự xử lý ngắt dòng hoặc ngắt trang bên trong nó
```
Lớp tiện ích	              CSS tương ứng	                Mô tả
break-inside-auto	          break-inside: auto;	          Giá trị mặc định, để trình duyệt tự quyết định ngắt hay không.
break-inside-avoid	        break-inside: avoid;	        Tránh ngắt nội dung bên trong phần tử.
break-inside-avoid-page	    break-inside: avoid-page;	    Tránh ngắt trang bên trong phần tử (thường dùng cho in ấn).
break-inside-avoid-column	  break-inside: avoid-column;	  Tránh ngắt cột bên trong phần tử (dùng khi làm việc với layout cột).
```
-> Sử dụng khi không muốn nội dung bị chia nhỏ khi in hoặc ngăn ngắt giữa các cột, grid hoặc nội dung bài bị chia nhỏ
### box-decoration-break: kiểm soát việc các phần tử được hiển thị trên nhiều dòng, cột hoặc trang (nó ảnh hưởng đến việc cách mà viền hoặc nền hiển thị khi phần tử của nó bị chia thành nhiều dòng)
```
box-decoration-clone              Nếu nội dung bị ngắt dòng, mỗi dòng sẽ có viền và nền riêng      
box-decoration-slice
```
### box-sizing: kiểm soát việc trình duyệt tính toán kích thước (chiều rộng, chiều cao) của một thẻ
```
Class                Style                              Mô tả
box-border           box-sizing: border-box             Khi dùng giá trị này thì chiều rộng và chiều cao của phần tử bao gồm cả padding và border  vd: thẻ có width = height = 100px, border = 2px, padding = 4px -> vùng hiển thị nội dung bằng 100 trừ đi border và padding 
box-content          box-sizing: content-box            (Mặc định) Khi dùng giá trị này thì kích thước của thẻ sẽ không bao gồm border và padding, vùng hiển thị nội dung sẽ có đúng kích thước được đặt
```
### display: kiểm soát cách hiển thị của phần tử và các phần tử con của nó tương tác với nhau
```
Class              Style                                  Mô tả
inline             display: inline                        Thiết lập phần tử là nôi tuyến (inline) -> chỉ chiếm không gian cần thiết và không bắt đầu trên một dòng mới
block              display: block                         Thiết lập phần tử là một khối (block - có chiều cao và rộng) -> chiếm toàn bộ chiều rộng có sẵn và bắt đầu trên một dòng mới
inline-block       display: inline-block                  Kết hợp giữa block và inline, cho phép phần tử có chiều cao và chiều rộng nhưng vẫn nằm trên cùng một dòng với các phần tử inline khác
flow-root          display: flow-root                     Tạo một khối chứa (block formatting context) cho các phần tử con của nó
flex               display: flex;                         Hiển thị phần tử như một inline flex container, cho phép sử dụng flexbox để bố trí các phần tử con
inline-flex        display: inline-flex;                  Tương tự như flex nhưng nó sẽ là một phần tử inline còn flex sẽ là một block
grid               display: grid;                         Thiết lập một phần tử là grid container
inline-grid        display: inline-grid;                  Tương tự như grid nhưng nó là một phần tử inline
contents           display: contents;                     Các phần tử con trong thẻ được sử dụng giá trị này được coi như thẻ con trực tiếp của thẻ chứa thẻ cha của chúng
table              display: table;                        Các phần tử trong nó hiển thị như một table
inline-table       display: inline-table;                 Giống như table nhưng nó là inline
table-caption      display: table-caption;                Là một phần tử caption của table
table-cell         display: table-cell;      
table-column       display: table-column;
table-column-group display: table-column-group;
table-footer-group display: table-footer-group;
table-header-group display: table-header-group;
table-row-group    display: table-row-group;
table-row          display: table-row;
list-item          display: list-item;                    Các phần tử con của nó hiển thị theo danh sách
hidden             display: none;                         Ẩn thi phần tử sử dụng giá trị này, không chiếm không gian

sr-only            position: absolute;                    Ẩn phần tử nhưng nó vẫn chiếm không gian
                    width: 1px;
                    height: 1px;
                    padding: 0;
                    margin: -1px;
                    overflow: hidden;
                    clip: rect(0, 0, 0, 0);
                    white-space: nowrap;
                    border-width: 0;

not-sr-only         position: static;                      Ngược lại của sr-only
                    width: auto;
                    height: auto;
                    padding: 0;
                    margin: 0;
                    overflow: visible;
                    clip: auto;
                    white-space: normal;
```
### Float: Điều chỉnh vị trí của phần tử trong bố cục
```
Class              Style                              Mô tả
float-right        float: right                       làm cho phần tử nổi về phía bên phải
float-left         float: left                        Làm cho phần tử nổi về phía bên trái
float-start        float: inline-start                Phần tử sẽ được hiển thị theo hướng văn bản và là inline
float-end          float: inline-end                  Phần tử sẽ hiển thị ngược lại hướng văn bản và là inline
float-none         float: none                        (Mặc định) Loại bỏ giá trị float được áp dụng
```
### clear: Kiểm soát cách mộ phần tử xử lý các phần tử float trước nó (Đảm bảo phần tử không nằm cạnh hoặc chồng lên các phần tử đã được gắn giá trị float)
```
Class              Style                              Mô tả
clear-left         clear: left                        Phần tử được gán giá trị không nằm cạnh phần tử có giá trị float-left (xuống dòng)
clear-right        clear: right                       Phần tử được gán giá trị không nằm cạnh phần tử có giá trị float-right
clear-both         clear: both                        Phần tử được gán giá trị không nằm cạnh cả float left và right
clear-start        clear: inline-start                Phần tử được gán sẽ có giá trị theo hướng của văn bản
clear-end          clear: inline-end                  Ngược hướng văn bản
clear-none         clear: none                        Không có giá trị nào được áp dụng
```
### isolation: Kiểm soát cách mà các phần tử chồng lên nhau và tương tác trong bố cục (nó ảnh hưởng tước giá trị z-index được áp dụng)
-> Ngữ cảnh xếp chồng (Stacking context): Mỗi ngữ cảnh xếp chống có thứ tự z-index riêng
-> khi nào sử dụng: Khi có các phần tử được xếp chồng nên nhau mà không muốn phần tử con nào đó kkhoong bị ảnh hưởng bởi các phần tử bên ngoài (như khi sử dụng z-index)
ta có thể sử dụng isolation-isolate để đảm bảo phần tử đó luôn nằm trên cùng hoặc không bị che khuất
```
Class              Style                              Mô tả
isolation-auto     isolation: auto                    Không tạo ra ngữ cảnh xếp chồng mới, đây là giá trị mặc định
isolation-isolate  isolation: isolate                 Tạo ra một Stacking context mới, các phần tử con bên trong sẽ không bị ảnh hưởng bởi các phần tử bên ngoài có thuộc tính z-index
```
### object-fit: sử dụng để điều chỉnh cách mà một hình ảnh hoặc video được hiển thị trong một phần tử chứa, đặc biệt là phần tử chứa có kích thước khác so với kích thước gốc của hình ảnh hoặc video
```
Class              Style                              Mô tả
object-contain     object-fit: contain;               Đảm bảo hình ảnh hoặc video sẽ được hiển thị trong phần tử mà không bị cắt xén. hình ảnh sẽ được thu nhỏ hoặc phóng to để phù hợp với phần tử chứa và giữ nguyên tỷ lệ của ảnh hoặc video
object-cover       object-fit: cover;                 Hình ảnh hoặc video sẽ phủ toàn bộ kích thước của phần tử chứa, nếu tỷ lệ không khớp thì hình ảnh hoặc video sẽ bị cắt xén
object-fill        object-fit: fill;                  Hình ảnh hoặc video được kéo giãn để lấp đầy phần tử chứa
object-none        object-fit: none;                  Không có bất kỳ tác động nào, nó sẽ được hiển thị với kích thước gốc của nó
object-scale-down  object-fit: scale-down;            Hình ảnh hoặc video sẽ được thu nhỏ nếu kích thước của nó lớn hơn phần tử chứa, nhưng nếu nó nhỏ hơn thì sẽ hiển thị ở kích thước gốc
```
### object-position: được sử dụng để điều chỉnh vị trí của ảnh hoặc video bên trong phần tử chứa nó
```
Class                          Style                                          Mô tả
object-bottom                  object-position: bottom;                       Ảnh hoặc video nằm ở vị trí dưới cùng - giữa của phần tử chứa nó
object-center                  object-position: center;
object-left                    object-position: left;
object-left-bottom             object-position: left bottom;
object-left-top                object-position: left top;
object-right                   object-position: right;
object-right-bottom            object-position: right bottom;
object-right-top               object-position: right top;
object-top                     object-position: top;
object-(<custom-property>)     object-position: var(<custom-property>);  
object-[<value>]               object-position: <value>;                      Tùy chỉnh vị trí vd: object-[25%, 50%] -> căn chỉnh ở 25% chiều ngang và 50% theo chiều dọc
```
### overflow: xử lý nội dung quá lớn so với phần tử chứa nó
```
Class                Style                      Mô tả
overflow-auto        overflow: auto;            Tự động thêm thanh scrollbar nếu nội dung vượt quá kích thước phần tử chứa nó     
overflow-hidden      overflow: hidden;          Ẩn đi nếu kích thước vượt quá
overflow-clip        overflow: clip;            Ẩn đi nếu kích thước vượt quá mà không cho thanh cuộn xuất hiện
overflow-visible     overflow: visible;         (Mặc định) Nội dung vượt quá kích thước của phần tử thì nội dung sẽ hiển trị ra ngoài
overflow-scroll      overflow: scroll;
overflow-x-auto      overflow-x: auto;
overflow-y-auto      overflow-y: auto;
overflow-x-hidden    overflow-x: hidden;
overflow-y-hidden    overflow-y: hidden;
overflow-x-clip      overflow-x: clip;
overflow-y-clip      overflow-y: clip;
overflow-x-visible   overflow-x: visible;
overflow-y-visible   overflow-y: visible;
overflow-x-scroll    overflow-x: scroll;
overflow-y-scroll    overflow-y: scroll;
```
### overscroll-behavior: kiểm soát hành vi của phần tử khi người dùng cuộn nội dung đến rìa của nó (boundary - ranh rới)
```
Class                  Style                                          Mô tả
overscroll-auto        overscroll-behavior: auto;                     (Giá trị mặc định) Sử dụng hành vi cuộn mặc định của trình duyệt, nếu cuộn đến rìa của phần tử thì có thể cuộn phần tử cha của phần tử đó
overscroll-contain     overscroll-behavior: contain;                  Giá trị này ngăn chặn việc cuộn trong khu vực chỉ định ảnh hưởng đến phần tử cha. Khi người dùng cuộn đến rìa của phần tử cuộn thì nó không kích hoạt sự kiện cuộn của cha
overscroll-none        overscroll-behavior: none;                     Ngăn chặn mọi hành vi cuộn tiếp tục khi đến ranh rới, không cho phép cuộn ra ngoài 
overscroll-x-auto      overscroll-behavior-x: auto;
overscroll-x-contain   overscroll-behavior-x: contain;
overscroll-x-none      overscroll-behavior-x: none;
overscroll-y-auto      overscroll-behavior-y: auto;
overscroll-y-contain   overscroll-behavior-y: contain;
overscroll-y-none      overscroll-behavior-y: none;
```
### position: kiểm soát cách một phần tử được định vị trong bố cục trang web
```
Class              Style                              Mô tả
static             position: static;                  (Mặc định) phần tử sẽ được định vị theo flow tự nhiên của tài liệu. Các thuộc tính top, right, bottom và left sẽ không có tác dụng
fixed              position: fixed;                   Phần tử được định vị cố định so với của sổ trình duyệt. Nó không cuộn cùng với nội dung mà sẽ luôn ở vị trí cố định. Không chiếm không gian
absolute           position: absolute;                Phần tử được định vị tuyệt đối so với phần tử cha gần nhất có thuộc tính position là static, relative, absolute (khác static). Nếu không có sẽ được định vị theo tài liệu. Không chiếm kgian
relative           position: relative;                Phần tử được định vị tương đối so với vị trí ban đầu của nó trong dòng chảy tài liệu. Các thuộc tính vị trí top, right ... có thể sử dụng để điều chỉnh vị trí
sticky             position: sticky;                  phần tử được định vị nhờ sự kết hợp của relative và fixed. Nó sẽ hoạt động như relative cho đến khi cuộn đến vị trí xác định và nó sẽ thành fixed
```
### top/right/bottom/left
```
Class              Style                              Mô tả
top-{number}       top: number                        Khoảng cách từ cạnh trên của phần tử tới cạnh trên của phần tử cha
right-{number}     right: number                      Khoảng cách từ cảnh phải của phần tử tới cạnh phải của phần tử cha
botton-{number}    bottom: number
left-{number}      left: number
-> các giá trị 1 = 0.25rem(4px), 2 = 0.5rem(8px) ...,
top-px -> top: 1px
top-1 -> top: 4px ...
top-1/2 -> top: 50% ...
top-full -> top: 100% ...
top-[number] giá trị tùy chỉnh cụ thể
-top-1 -> top: -4px

inset-*            top: *, right: *, left: *, bottom: *
inset-x-*          left: *, right: *
inset-y-*          top: *, bottom: *
```
### visibility: kiểm soát việc hiển thị của phần tử mà không làm thay đổi kích thước hoặc vị trí của nó trong bố cục
```
Class              Style                          Mô tả
visible	           visibility: visible;	          Hiển thị phần tử (mặc định).
invisible	         visibility: hidden;	          Ẩn phần tử nhưng vẫn chiếm không gian trong bố cục.
collapse	         visibility: collapse;	        Dùng trong bảng (table), ẩn hàng/cột và giải phóng không gian.   
```

## FLEXBOX & GRID
### Flex-basics: xác định kích thước ban đầu của một phần tử trong flexbox trước khi áp dụng các thuộc tính flex-grow và flex-shrink
- Đơn vị có thể sử dụng px, %, rem, em, auto, content, min-content, max-content, fit-content, v.v.
- Ưu tiên cao hơn width trong Flexbox: Nếu flex-basis được đặt, nó sẽ ghi đè width trừ khi width được đặt bằng auto.
```
Class              Style
```
```
Class              Style
```




























