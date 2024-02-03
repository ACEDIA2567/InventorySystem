# 인벤토리 시스템(임시)

## 많은 게임에서 

## 구현 사항
### 구현 할 것: 아이템과 저장한 아이템을 플레이어가 확인하는 UI 즉 인벤토리를 구현하고자 함
### 후에 구현할 것: 아이템과 인벤토리의 시스템이 이뤄지면 RPG와 시뮬레이션을 기반으로 발전시키고자 함
### 구현할 시스템: 아이템, 인벤토리, 가방, 플레이어

## 자세한 구현 내용
### 플레이어
#### 이동: WASD
#### 달리기: LShift
#### 아이템 획득: Z
#### 아이템 획득 절차
#### 1) 플레이어와 아이템의 거리가 일정 거리가 된다.
#### 2) 아이템 획득 키(Z)를 누른다.
#### 3) 플레이어의 인벤토리에 빈 공간이 있는지 확인한다.
#### 4) 빈 공간일 시 인벤토리 창의 첫 번째 빈 공간으로 아이템을 추가한다.
#### 5) 획득 한 아이템을 삭제 시킨다.

<br>

### 아이템
#### Name: 아이템의 이름
#### Type: 아이템의 종류(기타, 소비, 장비)
#### Image: 아이템의 그림
#### Num: 아이템의 식별 코드
#### Count: 아이템의 개수
#### 아이템의 개수는 인벤토리에 별도로 들어감(기타, 소비의 최대 아이템 개수:100 / 장비의 최대 아이템 개수:1)

<br>

### 인벤토리
#### 아이템 이동: 마우스(좌클릭)를 이용하여 아이템을 이동(드래그앤 드롭)을 시킨다.
#### ● 이동할 칸이 빈 공간 일 시: 아이템 정보를 이동할 빈 공간으로 이동시키고 이동했던 아이템의 정보를 삭제시킨다.
#### ● 이동할 칸에 같은 아이템이 존재할 시: 기타, 소비 아이템의 경우 아이템의 개수를 합치고 장비의 경우 정보를 이동하지 않는다.
#### 같은 아이템이 있는 곳으로 아이템 이동 시의 절차
#### > 1) 기타, 소비 아이템의 합친 개수가 100초과일 시: 이동한 아이템의 개수를 최대 값으로 변경하고 이동 된 아이템의 개수를 남은 아이템의 개수로 변경
#### > 2) 기타, 소비 아이템의 합친 개수가 100미만일 시: 이동한 아이템의 개수를 합치고 이동 된 아이템의 칸의 아이템의 정보를 삭제
#### ● 이동할 칸에 다른 아이템이 존재할 시: 서로의 아이템 정보를 교체한다.
#### ● 아이템을 인벤토리 밖으로 이동할 시: 아이템 삭제 여부 UI출력 후 긍정시 이동할 아이템 정보를 삭제

#### 인벤토리 <=> 가방
#### ● 이동할 칸이 빈 공간 일 시: 아이템 정보를 이동할 빈 공간으로 이동시키고 이동했던 아이템의 정보를 삭제시킨다.
#### ● 이동할 칸이 가방(같은 아이템 존재): 
#### 같은 아이템이 있는 곳으로 아이템 이동 시의 절차
#### 1) 기타, 소비 아이템의 합친 개수가 100초과일 시: 이동한 아이템의 개수를 최대 값으로 변경하고 이동 된 아이템의 개수를 남은 아이템의 개수로 변경
#### 2) 기타, 소비 아이템의 합친 개수가 100미만일 시: 이동한 아이템의 개수를 합치고 이동된 아이템의 칸의 아이템의 정보를 삭제
#### ● 이동할 칸에 다른 아이템 존재할 시: 서로의 아이템 정보를 교체한다.

#### 인벤토리 창 증가: 버튼 클릭시 인벤토리의 아이템 공간을 10개 증가시킨다.
#### 인벤토리 정렬: 아이템
#### 아이템 나누기: LShift를 누른 상태에서 아이템을 클릭한다.
#### 아이템 나누기 절차
#### 1) LShift를 누른 상태에서 아이템을 클릭한다.
#### 2) 인벤토리에 빈 공간이 있는지 확인한다.
#### 3) 빈 공간이 있을 시에 아이템을 나눌 수치를 입력하는 UI 활성화
#### 4) 수치를 입력하면 인벤토리의 첫 번째 빈 공간으로 아이템의 정보를 추가하고 개수를 수치로 변경한다.
