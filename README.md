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
### box-decoration-break: kiểm soát việc các phần tử được hiển thị trên nhiều dòng, cột hoặc trang





























