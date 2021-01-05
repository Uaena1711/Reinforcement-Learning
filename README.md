# Reinforcement-Learning
## 1. Value Iteration
   Bài 1 yêu cầu sinh viên phải viết một hàm lặp với tham số truyền vào là só lần lặp, hệ số discounted-nhằm để cho tổng trong chuỗi hội tụ, và mdp - một framework để biểu diễn. 
   Ý tưởng là ta tạo một vòng lặp bàng tham số truyền vào, lấy giá trị values (là trạng thái, action tại 1 vị trí nào đó của agents biểu diễn bằng số điểm). 
   Kiểm tra xem state hiện tại có phải kết thúc không, nếu đúng cập nhật value tại đó bằng hàm getReward. Nếu không dùng hàm getPossibleActions để lấy mọi hành đồng có thể thực hiện kèm với xác suất của nó. Cập nhật giá trị value theo công thức là max của Q-value từ các action đó. 
  Q value được cập nhật với công thức Reward + (max Qvalue tại các vị trí có thể đi tiếp *  discounted )
  Vậy ta có một vòng lặp để tính toán giá trị của từng trạng thái với hành động khác nhau, tiếp đó hàm computeActionFromValues sẽ quyết định phải đi theo đường nào bằng cách đi theo đường có giá trị Q lớn nhất .
    
