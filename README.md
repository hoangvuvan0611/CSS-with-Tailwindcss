# CSS-with-Tailwindcss
Project mô tả các trường css của taiwind

## Layout

### aspect-ratio: Kiểm soát tỷ lệ khung hình của một thẻ
Các giá trị áp dụng:
- square(hình vuông - dùng cho thẻ img, ...): aspect-1/1 (hoặc tỷ lệ tương ứng cho hình bất kỳ)
- video(dùng cho thẻ iframe để nhúng video,...): aspect-video (hoặc có thể cấu hình
tùy ý theo giá trị với cú pháp chung `aspect-[value]` vd: "aspect-[calc(4*3+1)/3]")
...
### columns: kiểm soát số lượng cột trong một phần tử
```
columns-<number>
columns: <number>;
columns-3xs
columns: var(--container-3xs); /* 16rem (256px) */
columns-2xs
columns: var(--container-2xs); /* 18rem (288px) */
columns-xs
columns: var(--container-xs); /* 20rem (320px) */
columns-sm
columns: var(--container-sm); /* 24rem (384px) */
columns-md
columns: var(--container-md); /* 28rem (448px) */
columns-lg
columns: var(--container-lg); /* 32rem (512px) */
columns-xl
columns: var(--container-xl); /* 36rem (576px) */
columns-2xl
columns: var(--container-2xl); /* 42rem (672px) */
columns-3xl
columns: var(--container-3xl); /* 48rem (768px) */
columns-4xl
columns: var(--container-4xl); /* 56rem (896px) */
columns-5xl
columns: var(--container-5xl); /* 64rem (1024px) */
columns-6xl
columns: var(--container-6xl); /* 72rem (1152px) */
columns-7xl
columns: var(--container-7xl); /* 80rem (1280px) */
columns-auto
columns: auto;
columns-(<custom-property>)
columns: var(<custom-property>);
columns-[<value>]
columns: <value>;
```
