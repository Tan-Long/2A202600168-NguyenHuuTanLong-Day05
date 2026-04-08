graph TD
    %% Nút gốc
    Root((VNA Neo Chatbot))

    %% Khu vực 1: 4 Paths User Journey
    subgraph "Luồng trải nghiệm (4 Paths) - Toàn Pain Points"
        direction TB
        
        P1[1. Khám phá & Tiếp cận] -->|Vấn đề| P1a(Tính năng bị giấu quá sâu)
        P1a --> P1b(App VNA -> Cuối trang chủ -> 'Cùng trải nghiệm')

        P2[2. Giao diện UI/UX] -->|Vấn đề| P2a(Sử dụng Webview chậm chạp)
        P2a --> P2b(Giao diện nhồi nhét quá nhiều chữ)
        P2a --> P2c(Cửa sổ chat chắn giữa màn hình)

        P3[3. Hiệu năng & Xử lý] -->|Vấn đề| P3a(Tốc độ phản hồi cực chậm)
        P3a --> P3b(Đơ, thiếu tín hiệu hệ thống đang xử lý)

        P4[4. Cá nhân hóa & Ngữ cảnh] -->|Vấn đề| P4a(Kiến thức cũ - Giới hạn 2025)
        P4a --> P4b(Không có Memory - Hỏi lại liên tục, 4 câu/lần)
        P4b --> P4c(Không kết nối dữ liệu chuyến bay user)
        P4c --> P4d(Bắt nhập thủ công mã vé/mã chuyến bay)
    end

    %% Khu vực 2: Gap Analysis
    subgraph "Gap Analysis (Kỳ vọng Marketing vs Thực tế)"
        direction LR
        
        G1{Dữ liệu & <br>Kiến thức} 
        G1 --- G1a[Kỳ vọng: Cập nhật real-time]
        G1 --- G1b[Thực tế: Outdated năm 2025]

        G2{Trải nghiệm <br>Mượt mà} 
        G2 --- G2a[Kỳ vọng: Native App tiện lợi]
        G2 --- G2b[Thực tế: Webview đứt gãy, UI lỗi]

        G3{Giao tiếp <br>Tự nhiên} 
        G3 --- G3a[Kỳ vọng: Có bối cảnh hội thoại]
        G3 --- G3b[Thực tế: Không memory, hỏi máy móc]

        G4{Cá nhân hóa <br>Trợ lý ảo} 
        G4 --- G4a[Kỳ vọng: Nhận diện user & data]
        G4 --- G4b[Thực tế: Rời rạc API, nhập tay dữ liệu]
    end

    %% Kết nối từ Gốc
    Root ===> P1
    Root ===> P2
    Root ===> P3
    Root ===> P4
    
    Root -.-> G1
    Root -.-> G2
    Root -.-> G3
    Root -.-> G4

    %% Định dạng màu sắc
    classDef error fill:#ffe6e6,stroke:#ff6666,stroke-width:2px,color:#000;
    classDef warning fill:#fff3cd,stroke:#ffc107,stroke-width:2px,color:#000;
    classDef success fill:#d4edda,stroke:#28a745,stroke-width:2px,color:#000;
    classDef core fill:#0055a4,stroke:#fff,stroke-width:3px,color:#fff;
    classDef default fill:#f8f9fa,stroke:#ced4da,stroke-width:1px,color:#000;

    class Root core;
    class P1a,P1b,P2a,P2b,P2c,P3a,P3b,P4a,P4b,P4c,P4d error;
    class G1b,G2b,G3b,G4b warning;
    class G1a,G2a,G3a,G4a success;


Tiêu chí,Kỳ vọng (Định vị/Marketing),Thực tế trải nghiệm (Theo ghi chú),Gap (Khoảng cách)
Mức độ thông minh (AI Knowledge),"Trợ lý ảo AI tiên tiến, cập nhật thông tin bay và chính sách real-time.",Dữ liệu huấn luyện (Knowledge) bị giới hạn (chỉ đến năm 2025).,Thiếu hụt dữ liệu mới nhất. AI chưa đủ khả năng trả lời chính xác các biến động thực tế.
Trải nghiệm liền mạch (Seamless Flow),"Ứng dụng công nghệ mượt mà, thao tác tiện lợi ngay trên điện thoại.","Phải load Webview chậm chạp, thiết kế UI cản trở tầm nhìn (chặn giữa màn hình).","Trải nghiệm bị đứt gãy, chắp vá, thiếu sự trau chuốt tinh tế của một sản phẩm Native App."
Giao tiếp tự nhiên (Conversational UX),"Trò chuyện như người thật, hiểu ngữ cảnh và nhớ luồng câu chuyện.","Không có bộ nhớ (Memory). Trả lời máy móc, hỏi lặp lại thông tin, ném cho user 4 câu hỏi cùng lúc.","Bot vẫn đang hoạt động theo dạng Rule-based (kịch bản cứng) yếu kém, chưa đạt chuẩn của một LLM có Context Window tốt."
Thấu hiểu người dùng (Personalization),"Trợ lý cá nhân, biết ""bạn là ai, bạn đang bay chuyến nào"".",Không kết nối database. Bắt user nhập tay mã vé và mã chuyến bay để tra cứu.,Hệ thống Backend và Bot bị cô lập (Data Silo). Thiếu tích hợp API nội bộ để định danh và hỗ trợ khách hàng tự động.
