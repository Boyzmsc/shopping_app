# 모바일 프로그래밍 개인 과제

**이 프로젝트는 국민대학교 모바일 프로그래밍 강의를 바탕으로 제작되었습니다.**

Nike 상품들을 품목으로 판매하는 모바일 쇼핑몰 앱

![화면 캡처 2020-11-16 214658](https://user-images.githubusercontent.com/28584213/99254176-48953000-2855-11eb-8859-71fd78601cc5.png)

------



### 목차

------

|   내용    |
| :-------: |
| 실행 화면 |
| 액티비티  |
| 레이아웃  |



### 실행 화면

------

##### 메인 페이지

![main](https://user-images.githubusercontent.com/28584213/99253872-d3c1f600-2854-11eb-9b76-a39fd7900343.png)


##### 장바구니 페이지

![wish](https://user-images.githubusercontent.com/28584213/99253876-d4f32300-2854-11eb-9c96-a92018082f40.png)


##### 구매 페이지

![purchase](https://user-images.githubusercontent.com/28584213/99253877-d58bb980-2854-11eb-91be-4f3b367f5bec.png)


### 액티비티

------

##### ListViewItem

- 상품몰에 추가할 아이템에 정보를 담은 class

* 상품에 대한 이미지, 상품명, 상품 가격의 변수를 가짐
* setter, getter 함수 구현
* 후에 ParcelableArrayListExtra를 위한 Parcelable 인터페이스를 implement한뒤 메서드 Override함



##### MainActivity

* 매인 액티비티 (첫번째 액티비티)
* 상품 선택 페이지를 나타냄
* 리스트 뷰에 있는 아이템 클릭 시 selectedItems 리스트에 추가됨
* 장바구니 페이지 (두번째 액티비티)에서 저장되어 있는 상품들을 인텐트로 받아옴
* 장바구니 버튼 클릭 시, 인텐트로 받은 상품들과 현재 페이지에서 선택한 상품들을 장바구니 페이지로 인텐트로 넘긴 뒤 장바구니 페이지로 이동
* 구매 버튼 클릭 시, 현재 페이지에서 선택한 상품들을 구매 페이지로 인텐트로 넘긴 뒤 구매 페이지로 이동
* 아무 상품도 선택 안하고 장바구니 버튼이나 구매 버튼 클릭 시 동작이 수행되지 않게끔 구현
* 커스텀 리스트뷰에 상품들을 추가하기 위한 어댑터 설정 및 추가 
* 뒤로가기 시 발생하는 Restart 상태를 위한 onRestart() 메서드 Override



##### MainListViewAdapter

* 메인 페이지 커스텀 리스트 뷰를 위한 어댑터 class
* 메인 페이지 커스텀 리스트 뷰에 포함하는 위젯들의 표시 상태 설정
* 상품들을 리스트뷰에 추가하는 addMainItem 메서드 작성



##### WishActivity

* 장바구니 액티비티 (두번째 액티비티)
* 장바구니 선택 페이지를 나타냄
* 리스트 뷰에 있는 아이템 클릭 시 purchaseItems 리스트에 추가됨
* 메인 페이지 (첫번째 액티비티)에서 선택되는 상품들을 인텐트로 받아옴
* 홈 버튼 클릭 시, 현재 페이지에 있는 상품들을 메인 페이지로 인텐트로 넘긴 뒤 메인 페이지로 이동 (장바구니에 담겨있는 상품들을 유지시키기 위해)
* 구매 버튼 클릭 시, 현재 페이지에서 선택한 상품들 구매 페이지로 인텐트로 넘긴 뒤 구매 페이지로 이동
* 아무 상품도 선택 안하고 구매 버튼 클릭 시 동작이 수행되지 않게끔 구현
* 커스텀 리스트뷰에 상품들을 표시하기 위한 어댑터 설정 및 추가 
* 뒤로가기 시 발생하는 Restart 상태를 위한 onRestart() 메서드 Override



##### WishListViewAdapter

* 장바구니 페이지 커스텀 리스트 뷰를 위한 어댑터 class
* 장바구니 페이지 커스텀 리스트 뷰에 포함하는 위젯들의 표시 상태 설정
* 상품들을 리스트뷰에 추가하는 addWishItem 메서드 작성



##### PurchaseActivity

* 구매 액티비티 (세번째 액티비티)
* 구매 페이지를 나타냄
* 구매할 상품의 총 개수와 총 금액을 텍스트뷰 위젯에 표시
* 메인 페이지 (첫번째 액티비티)에서 선택되는 상품들을 인텐트로 받아옴
  또는 장바구니 페이지 (두번째 액티비티)에서 선택되는 상품들을 인텐트로 받아옴
* 구매 확정 버튼 클릭 시, 매인 페이지로 이동
* 커스텀 리스트뷰에 상품들을 표시하기 위한 어댑터 설정 및 추가 
* 메인 페이지에서 구매 페이지로 뒤로가기 시 발생하는 Restart 상태를 위한 onRestart() 메서드 Override (구매 완료가 된 시점이므로 메인 페이지를 다시 불러오게끔 구현)



##### PurchaseListViewAdapter

* 구매 페이지 커스텀 리스트 뷰를 위한 어댑터 class
* 구매 페이지 커스텀 리스트 뷰에 포함하는 위젯들의 표시 상태 설정
* 상품들을 리스트뷰에 추가하는 addPurchaseItem 메서드 작성



##### CheckableLinearLayout

* 커스텀 리스트뷰에서 어느 부분을 클릭해도 클릭되게끔 만드는 class
* 또한 클릭 시 커스텀 리스트뷰에 있는 체크박스 표시 설정



### 레이아웃

------

##### activity_main

* 상품 선택 페이지의 레이아웃
* Relative Layout을 이용
* 리스트뷰와 버튼 위젯 사용



##### listview_item

* 상품 선택 페이지의 커스텀 리스트뷰 레이아웃
* 상품의 이미지와 상품명, 가격을 표시하기 위한 레이아웃 구성
* 위에서 정의한 CheckableLinearLayout 이용
* 이미지뷰, 텍스트뷰와 체크 박스 위젯 사용



##### wish_page

* 장바구니  페이지의 레이아웃
* Linear Layout을 이용
* 리스트뷰와 버튼 위젯 사용



##### listview_wish

* 장바구니 페이지의 커스텀 리스트뷰 레이아웃
* 상품명, 가격을 표시하기 위한 레이아웃 구성
* 위에서 정의한 CheckableLinearLayout 이용
* 텍스트뷰와 체크 박스 위젯 사용



##### purchase_page

* 구매  페이지의 레이아웃
* Table Layout을 이용
* 리스트뷰, 버튼, 텍스트 뷰, 텍스트 입력(주소 정보, 연락처) 위젯 사용



##### listview_purchase

* 구매 페이지의 커스텀 리스트뷰 레이아웃
* 상품명, 가격을 표시하기 위한 레이아웃 구성
* 텍스트뷰 위젯 사용



------

