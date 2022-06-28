# 물류최적화를 위한 데이터 생성

## Description
![KakaoTalk_20220628_173013427](https://user-images.githubusercontent.com/106570204/176133261-aa981ae1-5585-452b-9359-caa41b201728.png)
### summary
1. 주문 최적화에 사용될 주문 내역 데이터를 랜덤으로 생성
2. 주문내역을 이용하여 물류창고에 적재시킬 상품 내역 생성
3. 상품을 적재 시키기 위한 가상 물류 창고 생성
4. 생성된 물류 창고에 상품 적재  

## About Project  
![Language](https://user-images.githubusercontent.com/106570204/175895970-cbb4f497-8ad1-4bc5-8793-9a373a3dce78.png)
![Python](https://user-images.githubusercontent.com/106570204/175894722-311b34c7-d3bd-48d7-9584-6d65f3530e06.png)
### 주문 내역 생성  
* 적재데이터를 이용하여 column 가져오기  
* 적재데이터의 column에서 내역들을 unique하게 추출    
* 추출된 데이터들을 random하게 choice하여 주문 내역 생성  
* 연관된 컬럼의 내역들은 연결   
   1. 플랜트 - 플랜트명 - 매장코드 - 매장
   2. 상품코드 - 상품      

   <img src="https://user-images.githubusercontent.com/106570204/175899390-bb3c162b-08c9-4c43-b430-4a0e7e5b7495.png" width=60 height=20>
   <img src="https://user-images.githubusercontent.com/106570204/175899920-3953ada3-b73d-432b-be37-c2b1cbc87316.png" width=60 height=19>


### 상품 생성   
* 상품 생성에 필요한 핵심 column들만 남기고 slice  
* 물류 창고 적재에 필요한 column들 추가   
 ex) ABC, 단품가로, 세로, 높이, 중량  
* 추가된 column에 대한 내역도 random하게 생성
  
  <img src="https://user-images.githubusercontent.com/106570204/175899390-bb3c162b-08c9-4c43-b430-4a0e7e5b7495.png" width=60 height=20>
   <img src="https://user-images.githubusercontent.com/106570204/175899920-3953ada3-b73d-432b-be37-c2b1cbc87316.png" width=60 height=19>

### 물류 창고(MAP) 생성  
* 물류 창고 안에 존재할 선반 생성  
*<조건>*  
 물류 창고의 가장자리에는 선반이 존재하면 안됨  
선반끼리는 2칸의 여분 공간 필요  
공장 위쪽 아래쪽에 일정 간격으로 workstation 존재  

### 물류 창고 상품 적재  
* 상품 데이터(csv)를 받아 물류 창고에 적재  
*<조건>*  
상품코드로 물류 창고에 상품을 적재, 추출함  
선반에 60개 이상의 물건은 적재하지 않음  

## Result
### 주문 내역 생성 결과 
<img src="https://user-images.githubusercontent.com/106570204/176132582-b82d9be8-0b44-41ac-bdd6-fd4edb52c33f.png" width=100% height=400>

### 상품 생성 결과 
<img src="https://user-images.githubusercontent.com/106570204/176132916-e91797fd-84ab-4bab-83dd-3714445495e6.png" width=500 height=400>

### 가상 물류 창고 생성 결과   
|<img src="https://user-images.githubusercontent.com/106570204/176085575-237cddce-123b-47d4-8752-6dcf1dbe4acb.png" width=200 height=400>|R : 가로 <br> C : 세로 <br> W : Workstation <br> @ : 선반|<img src="https://user-images.githubusercontent.com/106570204/176086030-e0e12946-fb28-4e1b-a5cd-aff9a52cc937.png" width=200 height=400>|R : 가로 <br> C : 세로 <br> -1 : Workstation <br> n : 선반|
|---|---|---|---|


### 물류 창고 상품 적재 결과  
|물류 창고에 상품을 적재시킨 결과|1번 선반에 적재된 물건 확인|선반에 적재된 물건 추출 결과|
|---|---|---|
|<img src="https://user-images.githubusercontent.com/106570204/176088342-c6039c9f-5454-47c3-969a-8f7814b74a83.png" width=360 height=430>|<img src="https://user-images.githubusercontent.com/106570204/176088788-162874ea-fa13-4060-99ee-8897b747d684.png" width=360 height=450>|<img src="https://user-images.githubusercontent.com/106570204/176088848-0f3f0982-a6ac-400b-a759-224712f70a79.png" width=360 height=430>|   

|상품이 적재되어 있는 선반 위치 찾기 결과|
|---|
|<img src="https://user-images.githubusercontent.com/106570204/176137055-4e68e31e-73de-4a24-9788-b5aa621a66f4.png" width=100% height=200>|


## Reference
https://www.scirp.org/journal/ajor/
