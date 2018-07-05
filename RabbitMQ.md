Hướng dẫn cài đạt RabbitMQ trên Windows 10.

@Trước khi install RabbitMQ thì cần install erlang . Download ErLang 19.3 từ https://www.erlang.org/downloads/19.3
( Khi cài đặt erlang mới nhất thì đang bị lỗi không thể enable các plugin của RabbitMQ)

@Download RabbitMQ từ trang chủ và install bình thường.

@Setting biến môi trường :

ERLANG_HOME = C:\Program Files\erl8.3
RABBITMQ_SERVER = C:\Program Files\RabbitMQ Server\rabbitmq_server-3.7.6
RABBITMQ_HOME = C:\Program Files\RabbitMQ Server\rabbitmq_server-3.7.6 ( ??)
RABBITMQ_BASE = C:\Program Files\RabbitMQ Server\rabbitmq_server-3.7.6 ( ??)

Add thêm vào PATH = ;%RABBITMQ_SERVER%\sbin

@Chạy command bên dưới để enable plugin :

rabbitmq-plugins.bat enable rabbitmq_management

@Khởi động RabitMQ

rabbitmq-service.bat stop  
rabbitmq-service.bat install  
rabbitmq-service.bat start 

@Sau đó bạn có thể truy cập vào RabitMQ theo link sau http://localhost:15672. Enter login guest/guest

http://www.giaosucan.com/2018/01/kien-truc-message-queue-trong.html
