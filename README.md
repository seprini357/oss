# Trabill
다인원 여행 경비 관리 서비스

# Business purpose
## Project background
다인원이 함께하는 여행에서 교통비, 식비, 숙박비 등을 여러 사람이 번갈아 가며 결제하게 되면 각 지출마다 참여 인원이 다를 수 있으며 비용 분담 구조가 복잡해진다. 

지출 내역이 누적될수록 일일이 금액을 계산하고 정리하는 과정에서 번거로움이 발생하고 일부 지출 내역이 누락될 수도 있다. 

이를 토대로 모든 여행 참여자가 함께 여행 중 발생하는 비용을 체계적으로 기록 및 정산하며, 사용자 간 투명한 비용 공유를 하도록 한다.

## Goal
- 어플리케이션 기반의 여행 경비 관리 서비스 개발
- 모든 여행 참여자가 여행 경비를 기록하고 관리할 수 있는 시스템 구현
- 실시간 지출 내역 공유 및 정산 결과를 제공하여 투명한 비용 관리 환경 구축

## Target Market
2인 이상으로 국내여행을 떠나는 사람들을 주 대상자로 한다.


# System context diagram
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

## 1) Login
사용자가 자신의 계정으로 로그인한다.
|Actor| User|
| Purpose | 앱 사용을 위해 등록된 사용자인지 확인 |
| Approach | 사용자가 앱 실행 후 ID와 PW를 입력하면, 시스템은 DB에서 사용자 정보를 조회하여 로그인 성공 여부를 판단한다. |
| Dynamics | 앱 실행 → 로그인 시도 |
| Goals | 사용자 인증 기능 구현 |
