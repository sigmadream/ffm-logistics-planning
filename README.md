# 물류최적화를 위한 데이터 생성

## Description
![project_readme](https://user-images.githubusercontent.com/106570204/175852797-8f5df514-4d14-48d4-a6ae-c90723051d5b.png)
### summary
1. 주문 최적화에 사용될 주문 내역 데이터를 랜덤으로 생성
2. 주문내역을 이용하여 물류창고에 적재시킬 상품 내역 생성
3. 상품을 적재 시키기 위한 가상 물류 창고 생성
4. 생성된 물류 창고에 상품 적재  
---
## About Project  
![Language](https://user-images.githubusercontent.com/106570204/175895970-cbb4f497-8ad1-4bc5-8793-9a373a3dce78.png)
![Python](https://user-images.githubusercontent.com/106570204/175894722-311b34c7-d3bd-48d7-9584-6d65f3530e06.png)
### 주문 내역 생성  
* [적재데이터](#202204_출고_주문번호추가)를 이용하여 column 가져오기  
* 적재데이터의 column에서 내역들을 unique하게 추출    
* 추출된 데이터들을 random하게 choice하여 주문 내역 생성  
* 연관된 컬럼의 내역들은 연결   
  ex) 플랜트-플랜트명, 매장코드-매장, 상품코드-상품명  

   <img src="https://user-images.githubusercontent.com/106570204/175899390-bb3c162b-08c9-4c43-b430-4a0e7e5b7495.png" width=60 height=20>
   <img src="https://user-images.githubusercontent.com/106570204/175899920-3953ada3-b73d-432b-be37-c2b1cbc87316.png" width=60 height=20>


### 상품 생성   
* 상품 생성에 필요한 핵심 column들만 남기고 slice  
* 물류 창고 적재에 필요한 cloumn들 추가   
 ex) ABC, 단품가로, 세로, 높이, 중량  
* 추가된 column에 대한 내역도 random하게 생성
  
  <img src="https://user-images.githubusercontent.com/106570204/175899390-bb3c162b-08c9-4c43-b430-4a0e7e5b7495.png" width=60 height=20>
   <img src="https://user-images.githubusercontent.com/106570204/175899920-3953ada3-b73d-432b-be37-c2b1cbc87316.png" width=60 height=20>

### 물류 창고(MAP) 생성  
* 물류 창고 안에 존재할 선반 생성  
(조건)  
+물류 창고의 가장자리에는 선반이 존재하면 안됨  
+선반끼리는 2칸의 여분 공간 필요  
+오른쪽 가장자리에 워크스테이션 존재  
+선반에 60개 이상의 물건은 적재하지 않음  

### 물류 창고 상품 적재  
* 상품 데이터(csv)를 받아서 물류 창고에 적재  
(조건)  
+상품코드로 물류 창고에 상품을 적재, 추출함  
+선반에 60개 이상의 물건은 적재하지 않음  
---
## Result
