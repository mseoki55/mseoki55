<!-- 헤더 웨이브 배경 -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=667EEA&height=120&section=header"/>
</p>

<!-- 이름 + 직함 -->
<h1 align="center">🧑‍💻 송민석 (Song Min-seok)</h1>
<h3 align="center">Backend Developer | Spring Boot & Java 전문가 💪</h3>

<!-- 애니메이션 문구 -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&duration=3000&pause=1000&color=667EEA&center=true&vCenter=true&width=600&lines=Welcome+to+my+GitHub!;Spring+Boot+%26+Java+Backend+Developer;API+%26+Database+Design+Specialist+☕" alt="Typing SVG">
</p>

<!-- 기술 스택 배지 -->
<div align="center">
  <img src="https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL"/>
  <img src="https://img.shields.io/badge/AWS_S3-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS S3"/>
</div>

<!-- 개발자 이미지 -->
<p align="center">
  <img src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif" width="400" alt="Developer Coding">
</p>

---

## 🚀 **About Me**

> **Backend Developer** specializing in Spring Boot and Java development with a focus on RESTful API design and database architecture.

```java
public class SongMinseok {
    private String name = "송민석";
    private String role = "Backend Developer";
    private String email = "mseoki55@gmail.com";
    private String[] skills = {"Spring Boot", "JPA", "Spring Security", "MySQL"};
    private String passion = "Clean Code & Scalable Architecture";
    
    public void code() {
        while (true) {
            learn();
            build();
            deploy();
        }
    }
}
```

- 🌱 **Java 백엔드** 개발을 전문으로 하고 있습니다.
- 💡 **RESTful API 설계**와 **데이터베이스 아키텍처**에 집중합니다.
- ✨ **Spring Boot, JPA, Spring Security**를 활용한 안정적인 시스템 구축
- 🔥 목표는 **신뢰받는 백엔드 개발자**가 되는 것!
- 🎯 "꾸준함은 배신하지 않는다."는 마음으로 하루하루를 채워가고 있어요.

---

## 🎯 **Featured Project: Plit**

### 📋 **Project Overview**
- **프로젝트명**: Plit (게임 매칭/파티 시스템)
- **개발 기간**: 멀티캠퍼스 백엔드 3회차 부트캠프 최종 프로젝트
- **담당 역할**: 백엔드 API 개발 (클랜 & QnA 시스템)
- **기술 스택**: Spring Boot, JPA, Spring Security, MySQL, AWS S3

### 🏗️ **Architecture**
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Controller    │    │     Service     │    │   Repository    │
│   (REST API)    │◄──►│  (Business      │◄──►│   (Data Access) │
│                 │    │    Logic)       │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  Spring Security│    │   AWS S3        │    │     MySQL       │
│  (Auth/Author)  │    │  (File Upload)  │    │   (Database)    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

---

## 🛠️ **Core Features**

### 🏰 **Clan System API**
<details>
<summary><b>📁 Development Files</b></summary>

- `ClanController.java` (629 lines) - RESTful API endpoints
- `ClanService.java` - Business logic & transaction management
- `ClanRepository.java` - JPA data access layer
- `Clan Entity` - Domain model

</details>

<details>
<summary><b>⚙️ Key Features</b></summary>

- ✅ **CRUD Operations**: Complete clan management
- ✅ **Member Management**: Role-based access control
- ✅ **File Upload**: AWS S3 integration
- ✅ **Security**: Spring Security integration
- ✅ **Validation**: Request/Response validation

</details>

<details>
<summary><b>💻 Core API Example</b></summary>

```java
@PostMapping("/clan")
@PreAuthorize("hasRole('USER')")
public ResponseEntity<ClanResponse> createClan(
    @Valid @RequestBody ClanCreateRequest request,
    @AuthenticationPrincipal UserDetails userDetails) {
    
    Clan clan = clanService.createClan(request, userDetails);
    return ResponseEntity.status(HttpStatus.CREATED)
        .body(ClanResponse.from(clan));
}
```

</details>

### ❓ **QnA Management System API**
<details>
<summary><b>📁 Development Files</b></summary>

- `QnaController.java` (242 lines) - Admin API endpoints
- `QnaService.java` - Answer processing & email notifications
- `QnaRepository.java` - QnA data management
- `Qna Entity` - Domain model

</details>

<details>
<summary><b>⚙️ Key Features</b></summary>

- ✅ **CRUD Operations**: Complete QnA management
- ✅ **Answer System**: Admin response management
- ✅ **Email Notifications**: Automated email alerts
- ✅ **File Handling**: Upload and validation
- ✅ **Status Tracking**: QnA status management

</details>

<details>
<summary><b>💻 Core Service Example</b></summary>

```java
@Transactional
public void answerQna(Long qnaId, QnaAnswerRequest request) {
    Qna qna = qnaRepository.findById(qnaId)
        .orElseThrow(() -> new QnaNotFoundException());
    
    qna.updateAnswer(request.getAnswer());
    qna.updateStatus(QnaStatus.COMPLETED);
    
    // Send email notification
    emailService.sendQnaAnswerNotification(qna);
}
```

</details>

---

## 📸 **Project Screenshots**

### 🏰 **Clan System**
<div align="center">
  <img src="images/clan-detail.png" alt="Clan Detail Page" width="600"/>
  <p><em>클랜 상세 페이지 - 소개, 멤버 관리, 권한 제어</em></p>
</div>

<div align="center">
  <img src="images/clan-members.png" alt="Clan Members Management" width="600"/>
  <p><em>클랜 멤버 관리 - 11명의 멤버 정보 및 통계</em></p>
</div>

### ❓ **QnA Management System**
<div align="center">
  <img src="images/qna-user-history.png" alt="User QnA History" width="600"/>
  <p><em>사용자 문의 내역 - 문의 목록 및 상태 관리</em></p>
</div>

<div align="center">
  <img src="images/qna-detail.png" alt="QnA Detail View" width="600"/>
  <p><em>문의 상세보기 - 첨부파일, 상태, 답변 관리</em></p>
</div>

<div align="center">
  <img src="images/qna-admin.png" alt="Admin QnA Management" width="600"/>
  <p><em>관리자 문의 관리 - 전체 문의 목록 및 처리</em></p>
</div>

---

## 🎯 **Technical Challenges & Solutions**

| **Challenge** | **Solution** | **Technology** |
|---------------|--------------|----------------|
| **Complex DB Relationships** | JPA @ManyToMany, @OneToMany mapping | Spring Data JPA |
| **Secure File Upload** | MultipartFile + S3 SDK integration | AWS S3 |
| **Role-based Access Control** | Custom UserDetails + @PreAuthorize | Spring Security |
| **Email Notifications** | Spring Mail + SMTP configuration | Gmail SMTP |

---

## 📊 **Development Metrics**

<div align="center">

| **Metric** | **Value** | **Description** |
|------------|-----------|-----------------|
| **Backend Code** | `871 lines` | Controller + Service + Repository |
| **API Endpoints** | `15+` | CRUD + Business Logic |
| **Database Tables** | `8+` | Core entities & relationships |
| **Coverage** | `100%` | Backend responsibility |

</div>

---

## 🛠️ **Tech Stack**

### 💻 **Programming Languages**  
![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=white) 
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) 
![HTML](https://img.shields.io/badge/HTML5-E44D26?style=for-the-badge&logo=html5&logoColor=white) 
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

### 🧰 **Backend Tools & Frameworks**  
![Spring](https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white) 
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white) 
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=spring-security&logoColor=white)
![JPA](https://img.shields.io/badge/JPA-59666C?style=for-the-badge&logo=hibernate&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white) 
![AWS S3](https://img.shields.io/badge/AWS_S3-FF9900?style=flat-square&logo=amazonaws&logoColor=white)

### 🧑‍💻 **IDEs & Tools**  
![IntelliJ IDEA](https://img.shields.io/badge/IntelliJ%20IDEA-000000?style=for-the-badge&logo=intellijidea&logoColor=white) 
![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white) 
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white) 
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

## 🧠 **Most Used Languages**

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mseoki55&layout=donut&theme=dark&hide_border=true&size_weight=0.5&count_weight=0.5" />
</p>

---

## 📈 **GitHub Stats**

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=mseoki55&show_icons=true&theme=dark&hide_border=true" width="47%" />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=mseoki55&theme=dark&hide_border=true" width="47%" />
</p>

---

## 🎨 **Development Philosophy**

> **"Clean Code & Scalable Architecture"**

- 🔒 **Security First**: Spring Security for authentication & authorization
- 🏗️ **Layered Architecture**: Controller-Service-Repository pattern
- 📝 **RESTful Design**: Standard HTTP methods & status codes
- 🧪 **Test-Driven**: Unit tests for business logic
- 📚 **Documentation**: Clear API documentation

---

## 🌱 **현재 공부 중인 내용**

- 객체지향 프로그래밍 (OOP)의 원리 이해
- Java & Spring Boot 기반의 백엔드 구조
- MySQL 연동 및 JPA 고급 사용법
- AWS 클라우드 서비스 활용법
- 마이크로서비스 아키텍처 설계

---

## 🗂️ **앞으로 추가될 예정**

- 🛠 사이드 프로젝트
- 🧪 알고리즘 풀이 기록
- 📚 블로그나 기술 기록 링크
- 🚀 마이크로서비스 프로젝트

---

<!-- 푸터 애니메이션 -->
<h3 align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&duration=3000&pause=1000&color=667EEA&center=true&vCenter=true&width=600&lines=Thank+you+for+visiting+my+profile!;Let's+build+cool+things+together+🚀" alt="Footer Typing SVG" />
</h3>

<!-- 푸터 웨이브 -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=667EEA&height=120&section=footer"/>
</p>

<!-- 연락처 -->
<p align="center">
  📬 <strong>Contact</strong> &nbsp;|&nbsp;
  <a href="mailto:mseoki55@gmail.com">📧 mseoki55@gmail.com</a> &nbsp;|&nbsp;
  <a href="https://github.com/mseoki55">🔗 GitHub</a>
</p>

<p align="center">
  <em>"꾸준함은 배신하지 않는다 – 하루하루 성장하는 백엔드 개발자 💻"</em>
</p>
