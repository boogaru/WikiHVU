# Chống SQL injection
Sử dụng PDO để ràng buộc chống SQL injection. Hãy xem nó sẽ làm thế nào
Bình thường khi cần truy vấn :
`SELECT * FROM users WHERE email = 'minhbangchu@gmail.com'`
Người dùng có thể thêm 1 đoạn "or 1=1" vào sau câu truy vấn
`SELECT * FROM users WHERE email = 'minhbangchu@gmail.com' or 1=1`
Với câu này thì nó luôn đúng nên toàn bộ dữ liệu trong bảng users sẽ bị show ra.
Tuy nhiên với PDO thì câu truy vấn sẽ thành
`SELECT * FROM users WHERE email = 'minhbangchu@gmail.com or 1=1'`
Do đó sẽ trả về không có record nào
