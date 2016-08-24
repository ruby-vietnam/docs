*Q: Làm sao để có thể gọi một rake task từ một rake task khác?*

Xin chào mọi người

_Input:_

Mình có hai tasks được định nghĩa trong `Rakefile` như sau:


```
task :eat do |t|
  # do eating...
end

task :drink do |t|
  # do drinking..
end
```

Yêu cầu của biz là tạo một task thứ ba có tên `:all` để thực hiện 2 tasks kia

_Implementation:_

Mình copy tất cả nội dung của 2 tasks vào đưa nó vào task mới này

```
task :all do |t|
  # content of :eat
  # content of :drink
end
```

Có thể thấy là lặp lại nội dung không phải là pattern tốt

_Output_: 

Mình đang tìm cách nào để có thể gọi 2 task kia trực tiếp thay vì
sao chép lại nội dung, đại loại như sau

```
task :all do |t|
  # call :eat task
  # call :drink task
end
```

Xin cảm ơn
