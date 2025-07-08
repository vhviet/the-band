# 🧠 Bộ Câu Hỏi: Sử dụng React Component với TypeScript

---

## ❓ Câu hỏi 1: Cách viết nào tối ưu nhất để định nghĩa React Component với TypeScript?

**A. Sử dụng React.FC**

```tsx
const App: React.FC<{ message: string }> = ({ message }) => <div>{message}</div>;
```

**B. ✅ Sử dụng Arrow function thông thường**

```tsx
const App = ({ message }: { message: string }) => {
  return (<div>{message}</div>);
};
```

**C. Sử dụng React.FunctionComponent**

```tsx
const App: React.FunctionComponent<{ message: string }> = ({ message }) => (
  <div>{message}</div>
);
```

---

## ❓ Câu hỏi 2: Nếu bạn tham gia dự án React, định nghĩa `React.FC` cho component, bạn cần làm gì?

**A.**  
Update code sang `React.FunctionComponent` cho nó tường minh, thay vì viết tắt là `React.FC`.

**B.**  
Chẳng cần làm gì, vì nó vẫn hoạt động bình thường. Sửa lung tung, biết đâu sai thì sao.

**C. ✅**  
Migrate/Update code sang cách viết mới để tối ưu (ví dụ như sử dụng arrow function và không sử dụng `React.FC`).

---

## 📌 Ghi chú thêm:

- `React.FC` (hoặc `React.FunctionComponent`) **từng được dùng phổ biến**, nhưng hiện nay **không còn được khuyến nghị** trong hầu hết các team sử dụng TypeScript + React.
- Lý do:
  - Tự động thêm `children` dù không khai báo.
  - Làm việc với generic props phức tạp hơn.
  - Gây phụ thuộc vào kiểu của React không cần thiết.

✅ **Khuyến nghị hiện tại:** Sử dụng arrow function và khai báo kiểu props rõ ràng như sau:

```tsx
type Props = { message: string };

const App = ({ message }: Props) => {
  return <div>{message}</div>;
};
```