Để một hệ thống có thể xử lý hằng trăm nghìn sự kiện đồng thời (high-concurrency / high-throughput event processing), cần tối ưu từ kiến trúc, hạ tầng, đến code.

## 1. Kiến trúc hệ thống
**Microservices / Event-driven architecture**  

    - Chia nhỏ hệ thống, tách các thành phần độc lập, giao tiếp qua message queue (Kafka, RabbitMQ, NATS).

    - Giúp scale từng service theo nhu cầu xử lý riêng.
**Load balancing**

    - Dùng HAProxy, Nginx để phân phối request đều giữa nhiều instance
**CQRS + Event Sourcing**

    - (Command Query Responsibility Segregation) – Tách biệt trách nhiệm của lệnh (Command) và truy vấn (Query) trong hệ thống.
    - Chia đọc/ghi riêng để tránh bottleneck( tắc nghẽn cổ chai) trên database.

## 2. Hàng đợi & luồng xử lý (Messaging / Streaming)
## 3. Database

**Chọn DB phù hợp**

    Phù hợp tính đọc ghi của nghiệp vụ
    - Write: NoSQL
    - Read: ElasticSearch, Redis, ClickHouse (cho analytics).

**Tối ưu database**
    
    - Indexing
    - Partitioning
    - Connection pool
**Caching**

    - Redis/Memcached để giảm tải database cho dữ liệu thường xuyên truy cập


## 4. Ứng dụng & code

**Asynchronous / Non-blocking I/O**

    Tránh blocking thread khi chờ I/O.

**Tối ưu query**

## 5. Hạ tầng

**Horizontal scaling (scale-out)**

    - Đóng gói ( container ):Thuận lợi scale số lượng instance khi tải tăng

**Autoscaling**

    - Dựa vào CPU, memory, hoặc queue lag để tự động scale service.

## 6. Hệ thống giám sát

**Observability (Logs, Metrics, Traces)**

    - OpenTelemetry + Prometheus + Grafana để theo dõi throughput, latency, error rate.
