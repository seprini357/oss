# 💰 Trabill
다인원 여행 경비 지출 관리 앱
![image](https://github.com/user-attachments/assets/d613cc5c-2c76-4154-93d8-1b78570d1342)

---

# 1. Business purpose
## 📖 Project background
다인원이 함께하는 여행에서 교통비, 식비, 숙박비 등을 여러 사람이 번갈아 가며 결제하게 되면 각 지출마다 참여 인원이 다를 수 있으며 비용 분담 구조가 복잡해진다. 

지출 내역이 누적될수록 일일이 금액을 계산하고 정리하는 과정에서 번거로움이 발생하고 일부 지출 내역이 누락될 수도 있다. 

이를 토대로 모든 여행 참여자가 함께 여행 중 발생하는 비용을 체계적으로 기록 및 정산하며, 사용자 간 투명한 비용 공유를 하도록 한다.

## 🚀 Goal
- 어플리케이션 기반의 여행 경비 관리 서비스 개발
- 모든 여행 참여자가 여행 경비를 기록하고 관리할 수 있는 시스템 구현
- 실시간 지출 내역 공유 및 정산 결과를 제공하여 투명한 비용 관리 환경 구축

## 🎯 Target Market
2인 이상으로 국내여행을 떠나는 사람들을 주 대상자로 한다.

---

# 2. System context diagram
![image](https://github.com/user-attachments/assets/c9e7dfde-276c-4f5c-a4e6-617e8b43b379)
- Sign up: 회원가입
- Login: 로그인
- Create Group: 그룹 생성
- Join Group: 그룹 참여
- Add Expenses: 지출 등록
- Edit Expenses: 지출 수정
- Delete Expenses: 지출 삭제
- View Expenses: 지출 조회
- Request Settlement: 정산 요청
- View Results: 정산 결과 확인
- Authentication Confirmation: 로그인 인증 확인
- Created/Joined Group Status: 그룹 생성 및 참여 상태 
- Expense updates: 지출 내역 업데이트 내용 제공
- Settlement Results: 정산 결과 제공
- Store/Retrieve User, Group, Expense, Settlement Results: 사용자, 그룹, 지출, 정산 결과 저장 및 조회 
- Return Storage: 저장 결과
- Query Results: 조회 결과 반환
- Send Group Invite Notifications: 그룹 초대 알림 전송
- Send Expense Update Notifications: 지출 업데이트 알림 전송
- Send Settlement Completion Notifications: 정산 완료 알림 전송
- Return Notification Status: 알림 전송 결과 반환

---

# 3. Use-case and Concept of operation
## 1) Sign up
사용자가 회원가입을 한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 새로운 사용자를 시스템에 등록 |
| Approach | 사용자가 회원정보를 입력하면 해당 정보를 DB에 저장하고 계정을 생성 |
| Dynamics | 회원가입 요청 |
| Goals | 사용자 등록 기능 구현 |


## 2) Login
사용자가 자신의 계정으로 로그인한다.
| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 앱 사용을 위해 등록된 사용자인지 확인 |
| Approach | 사용자가 앱 실행 후 ID와 PW를 입력하면 DB에서 사용자 정보를 조회하여 로그인 여부를 판단 |
| Dynamics | 앱 실행 → 로그인 시도 |
| Goals | 사용자 인증 기능 구현 |


## 3) Create Group
사용자가 여행 경비를 관리하기 위한 여행 참여자 그룹을 생성한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 여행 경비 관리를 위한 여행 참여자 그룹 생성 |
| Approach | 사용자가 그룹 정보를 입력하면 그룹을 생성하고 DB에 저장 |
| Dynamics | 그룹 생성 요청 발생 |
| Goals | 그룹 관리 기능 구현 |


## 4) Join Group
사용자가 기존 여행 참여자 그룹에 참여한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 기존 여행 참여자 그룹 참여 |
| Approach | 사용자가 초대 코드를 입력하면 해당 그룹을 조회하여 참여 승인 |
| Dynamics | 그룹 참여 요청 발생 |
| Goals | 그룹 참여 기능 구현 |


## 5) Add Expenses
사용자가 여행 경비 지출 내역을 등록한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 여행 경비 지출 내역 기록 |
| Approach | 사용자가 지출 정보를 입력하면 해당 데이터를 DB에 저장 |
| Dynamics | 지출 등록 이벤트 발생 |
| Goals | 지출 관리 기능 구현 |


## 6) Edit Expenses
사용자가 기존 지출 내역을 수정한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 기존 지출 정보 수정 |
| Approach | 사용자가 수정 요청을 하면 해당 데이터를 업데이트 |
| Dynamics | 지출 수정 이벤트 발생 |
| Goals | 지출 수정 기능 구현 |


## 7) Delete Expenses
사용자가 불필요한 지출 내역을 삭제한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 불필요한 지출 내역 삭제 |
| Approach | 사용자가 삭제 요청을 하면 해당 데이터를 DB에서 제거 |
| Dynamics | 지출 삭제 이벤트 발생 |
| Goals | 지출 삭제 기능 구현 |


## 8) View Expenses
사용자가 그룹 내 지출 내역을 조회한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 그룹 내 지출 내역 확인 |
| Approach | DB에서 지출 데이터를 조회하여 사용자에게 제공 |
| Dynamics | 조회 요청 발생 |
| Goals | 지출 조회 기능 구현 |


## 9) Request Settlement
사용자가 정산 계산을 요청한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 정산 계산 수행 |
| Approach | 사용자가 경비 정산을 요청하면 시스템이 정산에 필요한 지출 데이터를 준비 |
| Dynamics | 정산 요청 이벤트 발생 |
| Goals | 제공할 정산 데이터 수집 |


## 10) Calculate Settlement 
시스템이 각 참여자의 분담 금액 및 총 지출액을 비교하여 최종 정산 금액을 계산한다.

| 항목 | 내용 |
|------|------------|
| Actor | System |
| Purpose | 참여자별 정산 계산 수행 |
| Approach | 시스템이 그룹 내 지출 데이터를 조회하여 각 참여자의 분담 금액과 총 지출액을 비교하여 최종 송금 및 수령 금액을 계산 |
| Dynamics | 정산 계산 수행 |
| Goals | 정확한 정산 로직 구현 |


## 11) View Settlement Results
사용자가 정산 결과를 확인한다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 정산 결과 확인 |
| Approach | 계산된 정산 결과를 사용자에게 제공 |
| Dynamics | 결과 조회 요청 발생 |
| Goals | 정산 결과 제공 기능 구현 |


## 12) Return Notification Status
사용자가 주요 이벤트에 대한 알림을 받는다.

| 항목 | 내용 |
|------|------------|
| Actor | User |
| Purpose | 주요 이벤트 알림 제공 |
| Approach | 그룹 초대, 지출 금액 변경, 정산 완료 시 Notification Service를 통해 알림 |
| Dynamics | 이벤트 발생 시 알림 전송 |
| Goals | 알림 기능 구현 |

---

# 4. Problem statment
## Technical Difficulties
- 복잡한 여행 경비 정산 로직
  - 사용자 별 지출 금액 및 분담 비율 등 여러 조건을 만족하며 최종 송금 및 수령 금액을 계산하는 알고리즘은 복잡하다.
- 데이터 일관성 유지
  - 여러 사용자가 동시에 지출을 등록, 수정, 삭제하여 race condition의 문제가 발생할 수 있다.
- 외부 API 연동
  - 알림 기능 구현으로 외부 API를 연동하여 외부 API 호출 실패를 고려하여 예외 처리가 필요하다.
## Non-Fuctional Requirements(NFRs)
- 정산 계산 결과는 요청 후 2초 이내에 제공되어야한다.
- DB 접근 후 데이터 조회 결과는 3초 이내에 화면에 표시되어야한다.
- 개인 정보와 금융 데이터는 안전하게 보호되어야한다.
- 직관적인 UI를 사용하여 모든 사용자가 사용할 수 있도록 한다.

---

# 5. Glossary
| 용어 | 내용 |
|------|------------|
| Trabill | 다인원 여행 경비 지출을 관리할 수 있는 서비스를 제공하는 앱 |
| Query | 데이터베이스에서 원하는 정보를 검색하기 위해 요청에 쓰이는 컴퓨터 언어 |
| Algorithm / 알고리즘 | 문제 풀이에 필요한 계산 절차 또는 처리 과정의 순서 |
| race condition |  공유 자원에 대해 여러 개의 프로세스가 동시에 접근을 시도할 때 접근의 타이밍이나 순서 등이 결과값에 영향을 줄 수 있는 상태 |
| Notification Service | 사용자에게 중요한 정보를 실시간으로 전달하는 시스템 |

---

# 6. References
- FCM(Firebase Cloud Messaging)
https://firebase.google.com/docs/cloud-messaging?hl=ko
