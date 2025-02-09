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
Class              Style                                Mô tả
basis-0	           flex-basis: 0px;	                    Kích thước ban đầu là 0px, phần tử sẽ phụ thuộc vào flex-grow.****
basis-1	           flex-basis: 0.25rem; /* 4px */	      Đặt kích thước ban đầu là 4px.
...
basis-96	         flex-basis: 24rem; /* 384px */	      Kích thước ban đầu là 384px.
basis-auto	       flex-basis: auto;	                  Kích thước tự động dựa vào nội dung.
basis-full	       flex-basis: 100%;	                  Phần tử sẽ chiếm toàn bộ chiều rộng hoặc chiều cao của container.
basis-1/2	         flex-basis: 50%;	                    Chiếm 50% chiều rộng hoặc chiều cao của container.
basis-[value]	     flex-basis: value;	                  Giá trị tùy chỉnh do người dùng đặt.
```
### flex-direction: được sử dụng để xác định hướng sắp xếp của các phần tử bên trong một flex container
```
Class                Style                              Mô tả
flex-row	           flex-direction: row;	              Các phần tử con được sắp xếp theo hàng ngang từ trái sang phải (mặc định).
flex-row-reverse	   flex-direction: row-reverse;      	Các phần tử con được sắp xếp theo hàng ngang nhưng đảo ngược, từ phải sang trái.
flex-col	           flex-direction: column;	          Các phần tử con được sắp xếp theo cột dọc, từ trên xuống dưới.
flex-col-reverse	   flex-direction: column-reverse;	  Các phần tử con được sắp xếp theo cột dọc nhưng đảo ngược, từ dưới lên trên.
```
### flex-wrap: được sử dụng để kiểm soát cách các phần tử con của một flex container sẽ hiển thị khi không đủ không gian
```
Class                Style                              Mô tả
flex-wrap	           flex-wrap: wrap;	                  Các phần tử có thể xuống dòng khi không đủ chỗ
flex-nowrap	         flex-wrap: nowrap;	                Các phần tử luôn nằm trên một hàng, có thể tràn ra ngoài
flex-wrap-reverse	   flex-wrap: wrap-reverse;	          Các phần tử có thể xuống dòng nhưng hàng mới sẽ xuất hiện phía trên
```
### flex: có tác dụng thiết lập phần tử thành flex container, nó kích hoạt flexbox để sắp xếp các phần tử con thành hàng ngang hay hàng dọc
```
Class              Style                          Mô tả
flex	             display: flex;	                Biến phần tử thành flex container
flex-1	            flex: 1 1 0%;	                Giãn đều, chiếm toàn bộ không gian trống
flex-auto	          flex: 1 1 auto;	              Giãn nhưng kích thước theo nội dung
flex-initial	      flex: 0 1 auto;	              Kích thước theo nội dung, không bắt buộc giãn
flex-none          	flex: 0 0 auto;	              Không co giãn, giữ nguyên kích thước
```
### flex-grow: điều chỉnh cách một phần tử con của một flex container mở rộng để lấp đầy không gian còn trống
```
Class              Style                           Mô tả
grow	             flex-grow: 1;	                  Phần tử mở rộng để chiếm không gian trống. Nếu có nhiều phần tử có grow, chúng sẽ chia đều không gian.
grow-0	           flex-grow: 0;	                  Phần tử không mở rộng, chỉ chiếm kích thước nội dung của nó.
grow-[n]	         flex-grow: n;	                  Sử dụng giá trị tùy chỉnh (n). Giúp điều chỉnh mức độ mở rộng của phần tử theo tỷ lệ mong muốn.
```
### flex-shrink: xác định mức độ một phần tử có thể co lại khi không đủ không gian trong container. Giá trị của nó càng cao thì phần tử càng co lại nhiều hơn so với các phần tử khác có giá trị thấp hơn
-> Sử dụng khi: 
- Muốn một số phần tử flex container giữ nguyên kích thước và không bị co lại
- Khi muốn ưu tiên một số phần tử co lại nhiều hơn so với những phần tử khác
- Cần tùy chỉnh độ co giãn của từng phần tử để giao diện đẹp hơn trên các kích thước màn hình khác nhau
```
Class                      Style                          Mô tả
shrink hoặc shrink-1	      flex-shrink: 1;	              Phần tử có thể co lại khi không đủ không gian (mặc định).
shrink-0	                  flex-shrink: 0;	              Phần tử không co lại khi không đủ không gian.
shrink-2	                  flex-shrink: 2;	              Phần tử co lại gấp đôi so với phần tử có shrink-1.
shrink-3	                  flex-shrink: 3;	              Phần tử co lại gấp ba lần so với shrink-1.
shrink-4	                  flex-shrink: 4;	              Phần tử co lại gấp bốn lần so với shrink-1.
shrink-5	                  flex-shrink: 5;	              Phần tử co lại gấp năm lần so với shrink-1.
```
### order: được sử dụng để thay đổi thứ tự hiển thị của các phần tử trong flexbox hoặc grid, mặc định tất cả các phần tử có giá trị order: 0
```
Class              Style                            Mô tả
order-1	            order: 1;	                      Phần tử này sẽ được đặt sau các phần tử có order: 0 (mặc định).
order-2	            order: 2;	                      Phần tử này sẽ được đặt sau phần tử có order: 1.
...
order-12	          order: 12;	                    Phần tử này sẽ được đặt sau phần tử có order: 11.
order-first	        order: -9999;	                  Luôn đặt phần tử này lên đầu cùng.
order-last	        order: 9999;	                  Luôn đặt phần tử này ở cuối cùng.
order-none	        order: 0;	                      Giữ nguyên thứ tự mặc định (giá trị mặc định của CSS).
```
### grid-template-columns: được sử dụng để xác định số lượng cột và cách chia chiều rộng của các cột trong css grid layout. Nó được sử dụng thông qua các lớp có tiền tố grid-cols-{n} hoặc grid-cols-{keyword}.
```
Class              Style                                Mô tả
grid-cols-n	                                            Xác định số lượng cột từ 1-12
grid-cols-none	                                        Xóa toàn bộ cột, loại bỏ cấu trúc grid column, cho phép các phần tử con tự sắp xếp
grid-cols-subgrid	                                      Kế thừa lưới cha (chỉ hoạt động trên Firefox), cho phép grid con kế thừa các column từ grid cha
grid-cols-[value]	                                      Xác định kích thước cột tùy chỉnh cho từng cột, vd: grid-cols-[100px,_1fr,_2fr]
grid-cols-[repeat(n, size)]	                            Lặp lại cột có kích thước tương tự, vd: grid-cols-[repeat(3,_200px)]
grid-cols-[repeat(auto-fill, minmax(min, max))]	        Tự động điền cột dựa trên kích thước tối thiểu và tối đa
grid-cols-[repeat(auto-fit, minmax(min, max))]	        Tự động co giãn cột
grid-cols-[var(--custom-property)]	                    Sử dụng biến CSS
```
### grid-column: kiểm soát cách một số phần tử mở rộng trên các cột trong lưới
```
Class                    Style                                Mô tả
col-auto	                grid-column: auto;	                Phần tử mở rộng theo nội dung hoặc tự động.
col-span-1	              grid-column: span 1 / span 1;	      Phần tử chiếm đúng 1 cột.
...
col-span-12	              grid-column: span 12 / span 12;	    Phần tử mở rộng 12 cột.
col-span-full	            grid-column: 1 / -1;	              Phần tử mở rộng toàn bộ hàng lưới.

- Định vị phần tử trong lưới
col-start-1	              grid-column-start: 1;	              Bắt đầu từ cột thứ 1.
col-start-2	              grid-column-start: 2;	              Bắt đầu từ cột thứ 2.
col-start-3	              grid-column-start: 3;	              Bắt đầu từ cột thứ 3.
-col-start-3
...	...	...
col-start-13	            grid-column-start: 13;	            Bắt đầu từ cột thứ 13 (nếu có 12 cột).
col-end-1	                grid-column-end: 1;	                Kết thúc tại cột thứ 1.
col-end-2	                grid-column-end: 2;	                Kết thúc tại cột thứ 2.
col-end-3	                grid-column-end: 3;	                Kết thúc tại cột thứ 3.
...	...	...
col-end-13	              grid-column-end: 13;	              Kết thúc tại cột thứ 13.
col-end-auto	            grid-column-end: auto;	            Kết thúc tự động dựa trên nội dung.
```
### grid-template-rows: được sử dụng để xác định số hàng và kích thước của các hàng trong một css grid
```
Class                    Style                                                    Mô tả
grid-rows-1	              grid-template-rows: repeat(1, minmax(0, 1fr));	        1 hàng chiếm toàn bộ không gian
grid-rows-2	              grid-template-rows: repeat(2, minmax(0, 1fr));	        2 hàng có kích thước bằng nhau
grid-rows-none	          grid-template-rows: none;	                              Không sử dụng grid hàng
grid-rows-auto	          grid-template-rows: auto;	                              Kích thước hàng tự động theo nội dung
grid-rows-[custom]	      grid-template-rows: custom;	                            Xác định giá trị tùy chỉnh (CSS Grid)
```
### grid-row: kiểm soát vị trí và phạm vị của một phần tử trong lưới grid. Nó giúp xác định phần tử đó bắt đầu từ hàng nào và kéo dài qua bao nhiêu hàng trong hệ thống CSS grid
```
Class                      Style                              Mô tả
row-{start}/{end}
row-{value}
row-start-{n}                                            Xác định hàng bắt đầu của phần tử {n} là một số nguyên từ 1 trở lên, tùy thuộc vào số hàng được khai báo trong grid-template-rows
row-end-{n}                                              Xác định hàng kết thúc của phần tử.
row-auto                                                 Mặc định, tự động sắp xếp theo grid.
row-span-{n}                                             Kéo dài phần tử qua {n} hàng.
row-span-full                                            Kéo dài phần tử từ hàng đầu tiên đến hàng cuối cùng.
```
### grid-auto-flow: được sử dụng để kiểm soát cách các phần tử con trong grid được đặt vào bố cục khi không có vị trí cụ thể nào được chỉ định
```
Class                    Style                              Mô tả
grid-flow-row	            grid-auto-flow: row;	            Sắp xếp các phần tử theo hàng (row), nghĩa là phần tử tiếp theo sẽ được đặt ở hàng tiếp theo nếu hàng hiện tại đã đầy. Đây là giá trị mặc định của grid.
grid-flow-col	            grid-auto-flow: column;	          Sắp xếp các phần tử theo cột (column), nghĩa là phần tử tiếp theo sẽ được đặt ở cột tiếp theo nếu cột hiện tại đã đầy.
grid-flow-dense	          grid-auto-flow: row dense;	      Sắp xếp các phần tử theo hàng và đồng thời sử dụng cơ chế "dense" để lấp đầy các khoảng trống có thể có trong grid (tức là các phần tử có thể bị đẩy lên trên nếu có chỗ trống).
grid-flow-row-dense	      grid-auto-flow: row dense;	      Giống grid-flow-dense, nhưng cụ thể hơn là sắp xếp theo hàng trước.
grid-flow-col-dense	      grid-auto-flow: column dense;	    Sắp xếp các phần tử theo cột nhưng đồng thời cố gắng lấp đầy khoảng trống.
```
### grid-auto-columns: sử dụng để xác định kích thước tự động của các cột trong grid container khi các cột được tạo tự động mà không có kích thước rõ ràng. Tốt khi có các phần tử con nhưng không xác định được số lượng cột cụ thể
```
Class              Style                                    Mô tả
auto-cols-auto	    grid-auto-columns: auto;	              Kích thước tự động dựa trên nội dung bên trong.
auto-cols-min	      grid-auto-columns: min-content;	        Cột sẽ có kích thước nhỏ nhất cần thiết để hiển thị nội dung.
auto-cols-max	      grid-auto-columns: max-content;	        Cột sẽ có kích thước lớn nhất có thể mà không bị tràn.
auto-cols-fr	      grid-auto-columns: minmax(0, 1fr);	    Cột có thể mở rộng để lấp đầy không gian trống theo tỉ lệ fr.
```
### grid-auto-rows: dùng để xác định chiều cao tự động của các hàng trong css grid khi hàng đó không được khai báo rõ ràng
```
Class                              Style                                            Mô tả
auto-rows-auto                      grid-auto-rows: auto;                           Hàng tự động điều chỉnh theo nội dung
auto-rows-min                       grid-auto-rows: min-content;                    Hàng nhỏ nhất có thể (min-content), chiều cao nhỏ nhất có thể chứa nội dung
auto-rows-max                       grid-auto-rows: max-content;                    Hàng lớn nhất có thể (max-content)
auto-rows-fr                        grid-auto-rows: minmax(0, 1fr);                 Chia đều không gian còn lại
auto-rows-(<custom-property>)       grid-auto-rows: var(<custom-property>);         Hàng có thể mở rộng từ 0 đến tối đa nội dung
auto-rows-[<value>]                 grid-auto-rows: <value>;
```
### gap: được sử dụng để thiết lập khoảng cách giữa các phần tử con trong flexbox hoặc grid
```
Class              Style                                    Mô tả
gap-{size}                                                  Áp dụng khoảng cách cho cả chiều ngang và dọc.
gap-0	              gap: 0px;
gap-px	            gap: 1px;
gap-0.5	            gap: 2px;
gap-1	              gap: 4px;
gap-x-{size}                                                Chỉ áp dụng khoảng cách theo trục ngang (cột).
gap-y-{size}                                                Chỉ áp dụng khoảng cách theo trục dọc (hàng).
```
### justify-content: sử dụng để căn chỉnh các phần tử con theo trục chính trong một flex container (display: flex) hoặc grid container
```
Class                    Style                                       Mô tả
justify-start	            justify-content: flex-start;	              Căn các phần tử con về phía đầu (trái nếu là row, trên nếu là column).
justify-end	              justify-content: flex-end;	                Căn các phần tử con về phía cuối (phải nếu là row, dưới nếu là column).
justify-center	          justify-content: center;	                  Căn giữa các phần tử con theo trục chính.
justify-between	          justify-content: space-between;  	          Các phần tử con được dàn đều, phần tử đầu và cuối nằm sát mép.
justify-around	          justify-content: space-around;	            Các phần tử con được dàn đều với khoảng trống hai bên mỗi phần tử.
justify-evenly	          justify-content: space-evenly;	            Các phần tử con được dàn đều với khoảng trống bằng nhau giữa chúng.
justify-stretch	          justify-content: stretch;	                  (Chỉ áp dụng cho grid) Các phần tử con sẽ kéo giãn để lấp đầy trục chính.
justify-baseline	        justify-content: baseline;	                (Chỉ áp dụng cho grid) Căn các phần tử theo đường cơ sở của chúng.
justify-normal	          justify-content: normal;	                  Sử dụng hành vi mặc định để phân bố các phần tử trên trục chính.
```
### justify-items: sử dụng để kiểm soát cách các phần tử trong một grid container được căn chỉnh theo trục ngang
```
Class                    Style                            Mô tả
justify-items-start       justify-items: start;            Căn các phần tử lưới về phía đầu của trục ngang.
justify-items-end         justify-items: end;              Căn các phần tử lưới về phía cuối của trục ngang.
justify-items-center      justify-items: center;           Căn giữa các phần tử lưới theo trục ngang.
justify-items-stretch     justify-items: stretch;          Kéo giãn các phần tử lưới để lấp đầy không gian theo trục ngang.
justify-items-normal      justify-items: normal;           Sử dụng hành vi căn chỉnh mặc định của trình duyệt cho các phần tử lưới.
```
-> Thuộc tính justify-items chỉ áp dụng cho các container sử dụng CSS Grid. Đối với Flexbox, để căn chỉnh các phần tử theo trục ngang, bạn nên sử dụng thuộc tính justify-content cho container và justify-self cho các phần tử con.
### justify-self: sử dụng để căn chỉnh một phần tử con trong một grid container dọc theo trục ngang. Cho phép điều chỉnh vị trí của từng phần tử con một cách độc lập thay vì ấp dụng cho tất các các phần tử con
```
Class                        Style                            Mô tả
justify-self-auto	            justify-self: auto;	            Sử dụng giá trị căn chỉnh mặc định hoặc kế thừa từ thuộc tính justify-items của container.
justify-self-start	          justify-self: start;	          Căn phần tử về phía đầu của trục ngang trong ô lưới.
justify-self-end	            justify-self: end;	            Căn phần tử về phía cuối của trục ngang trong ô lưới.
justify-self-center	          justify-self: center;	          Căn phần tử vào giữa trục ngang trong ô lưới.
justify-self-stretch	        justify-self: stretch;	        Kéo giãn phần tử để lấp đầy toàn bộ chiều rộng của ô lưới.
```
-> Các lớp justify-self chỉ áp dụng cho các phần tử trong container lưới (display: grid). Đối với container flex (display: flex), thuộc tính justify-self không có tác dụng. Thay vào đó, bạn có thể sử dụng thuộc tính align-self để căn chỉnh các phần tử con trong container flex.
### align-content: được sử dụng đẻ căn chỉnh các hàng trong một container flex hoặc grid có nhiều dòng dọc theo trục dọc (cross axis)
```
Class                        Style                            Mô tả
content-normal	              align-content: normal;	        Sử dụng căn chỉnh mặc định.
content-center	              align-content: center;	        Căn giữa các hàng theo trục chéo.
content-start	                align-content: flex-start;	    Căn các hàng về phía đầu của trục chéo (trên cùng).
content-end	                  align-content: flex-end;	      Căn các hàng về phía cuối của trục chéo (dưới cùng).
content-between	              align-content: space-between;	  Phân bố các hàng với khoảng cách đều nhau giữa chúng, không có khoảng trống ở đầu và cuối.
content-around	              align-content: space-around;	  Phân bố các hàng với khoảng cách đều nhau xung quanh mỗi hàng, bao gồm cả đầu và cuối.
content-evenly	              align-content: space-evenly;	  Phân bố các hàng với khoảng cách bằng nhau giữa tất cả các hàng, bao gồm cả đầu và cuối.
content-baseline	            align-content: baseline;	      Căn các hàng theo đường cơ sở của chúng.
content-stretch	              align-content: stretch;	        Kéo giãn các hàng để lấp đầy không gian trục chéo (mặc định).
```
### align-items: được sử dụng để căn chỉnh các phần tử con dọc theo trục chéo (cross axis) trong một flex container (display: flex) hoặc grid container (display: grid). Các lớp tiện ích của Tailwind cho thuộc tính này bắt đầu bằng items-.
```
Class                        Style                            Mô tả
items-start	                  align-items: flex-start;	      Căn các phần tử con về phía đầu của trục chéo (trên cùng đối với trục dọc).
items-end	                    align-items: flex-end;	        Căn các phần tử con về phía cuối của trục chéo (dưới cùng đối với trục dọc).
items-center	                align-items: center;	          Căn giữa các phần tử con dọc theo trục chéo.
items-baseline	              align-items: baseline;	        Căn các phần tử con theo đường cơ sở của chúng, hữu ích khi làm việc với văn bản có kích thước khác nhau.
items-stretch	                align-items: stretch;	          Mặc định, kéo giãn các phần tử con để lấp đầy không gian trục chéo.
```
### align-self: được sử dụng để điều chỉnh cách một phần tử flex hoặc grid cụ thể được căn chỉnh dọc theo trục chéo (cross axis) của container chứa nó. Điều này cho phép bạn ghi đè giá trị align-items được đặt trên container cho từng phần tử riêng lẻ. 
```
Class                        Style                            Mô tả
self-auto	                    align-self: auto;	              Phần tử sẽ tuân theo giá trị align-items của container.
self-start	                  align-self: flex-start;	        Căn phần tử về phía đầu của trục chéo trong container.
self-end	                    align-self: flex-end;	          Căn phần tử về phía cuối của trục chéo trong container.
self-center	                  align-self: center;	            Căn phần tử vào giữa trục chéo trong container.
self-stretch	                align-self: stretch;	          Kéo giãn phần tử để lấp đầy không gian dọc theo trục chéo của container.
self-baseline	                align-self: baseline;	          Căn phần tử theo đường cơ sở (baseline) của trục chéo trong container.
```
### place-content: là một tiện ích cho phép bạn kiểm soát cách nội dung trong một container flex hoặc grid được căn chỉnh và phân bố theo cả trục chính (main axis) và trục phụ (cross axis) cùng một lúc. Nó là một cách viết tắt kết hợp của hai thuộc tính CSS: align-content và justify-content. 
```
Class                        Style                            Mô tả
place-content-center	        place-content: center;	        Căn giữa nội dung theo cả trục chính và trục phụ.
place-content-start	          place-content: start;	          Căn nội dung về phía đầu của cả hai trục.
place-content-end	            place-content: end;	            Căn nội dung về phía cuối của cả hai trục.
place-content-between	        place-content: space-between;	  Phân bố nội dung với khoảng cách đều giữa các phần tử theo cả hai trục.
place-content-around	        place-content: space-around;	  Phân bố nội dung với khoảng cách đều xung quanh mỗi phần tử theo cả hai trục.
place-content-evenly	        place-content: space-evenly;	  Phân bố nội dung với khoảng cách bằng nhau giữa các phần tử theo cả hai trục.
place-content-stretch	        place-content: stretch;	        Kéo giãn nội dung để lấp đầy không gian theo cả hai trục.
```
### place-items: được sử dụng để căn chỉnh các phần tử con theo cả trục chính (main axis) và trục phụ (cross axis) trong một container sử dụng CSS Grid. Nó kết hợp hai thuộc tính align-items và justify-items, cho phép bạn kiểm soát cách các phần tử con được căn chỉnh theo cả hai trục cùng một lúc.
```
Class                        Style                            Mô tả
place-items-start	            place-items: start;	            Căn các phần tử con về phía đầu của cả trục chính và trục phụ.
place-items-end	              place-items: end;	              Căn các phần tử con về phía cuối của cả trục chính và trục phụ.
place-items-center	          place-items: center;	          Căn giữa các phần tử con theo cả trục chính và trục phụ.
place-items-baseline	        place-items: baseline;	        Căn các phần tử con theo đường cơ sở (baseline) của chúng.
place-items-stretch	          place-items: stretch;	          Kéo giãn các phần tử con để lấp đầy không gian theo cả trục chính và trục phụ.
```
### place-self: được sử dụng để căn chỉnh một phần tử con duy nhất trong một container flex hoặc grid. Nó kết hợp hai thuộc tính align-self và justify-self, cho phép bạn điều chỉnh vị trí của phần tử theo cả trục chính và trục chéo. Điều này hữu ích khi bạn muốn một phần tử cụ thể có cách căn chỉnh khác với các phần tử khác trong cùng container.
```
Class                        Style                            Mô tả
place-self-auto	              place-self: auto;	              Phần tử sẽ tuân theo giá trị của thuộc tính place-items của container.
place-self-start	            place-self: start;	            Căn phần tử về phía đầu của cả trục chính và trục chéo.
place-self-end	              place-self: end;	              Căn phần tử về phía cuối của cả trục chính và trục chéo.
place-self-center	            place-self: center;	            Căn giữa phần tử trên cả hai trục.
place-self-stretch	          place-self: stretch;	          Kéo giãn phần tử để lấp đầy không gian trên cả hai trục.
```
```
Class                        Style                            Mô tả
```
```
Class                        Style                            Mô tả
```

```
Class                        Style                            Mô tả
```



























