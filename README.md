# Reinforcement-Learning
## 1. Value Iteration
   Bài 1 yêu cầu sinh viên phải viết một hàm lặp với tham số truyền vào là só lần lặp, hệ số discounted-nhằm để cho tổng trong chuỗi hội tụ, và mdp - một framework để biểu diễn. 
   Ý tưởng là ta tạo một vòng lặp bàng tham số truyền vào, lấy giá trị values (là trạng thái, action tại 1 vị trí nào đó của agents biểu diễn bằng số điểm). 
   Kiểm tra xem state hiện tại có phải kết thúc không, nếu đúng cập nhật value tại đó bằng hàm getReward. Nếu không dùng hàm getPossibleActions để lấy mọi hành đồng có thể thực hiện kèm với xác suất của nó. Cập nhật giá trị value theo công thức là max của Q-value từ các action đó. 
  Q value được cập nhật với công thức Reward + (max Qvalue tại các vị trí có thể đi tiếp *  discounted )
  Vậy ta có một vòng lặp để tính toán giá trị của từng trạng thái với hành động khác nhau, tiếp đó hàm computeActionFromValues sẽ quyết định phải đi theo đường nào bằng cách đi theo đường có giá trị Q lớn nhất .
    
### 2. Bridge Crossing Analysis
    Như đã thấy trong hình vẽ, tác tử của chúng ta xuất phát từ nơi gần điểm thấp và mục tiêu là đi đến nơi có điểm cao với đường đi đến đó có dạng 1 caay cầu gồm các value có giá trị thấp, quan đó là hàng loạt các ô có điểm -100 (điểm cực thấp). Hệ số answerNoise dùng để thay đổi đường đi của tác tử dù theo kết quả tính toán lẽ ra nó phải đi theo hướng nào đó. Nhằm đảm bảo khi Q tính không được tối ưu thì nó vẫn ra kết quả. Chuyển hệ số này về 0 tác tử sẽ đi như 
