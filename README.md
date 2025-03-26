# food-recommendation-system
응용소프트웨어실습 팀 프로젝트

## User Table
| 컬럼명              | 타입                                                   | 설명                                                |
|-------------------|------------------------------------------------------|---------------------------------------------------|
| user_id           | INT (PK)                                              | 유저 고유 ID                                         |
| gender            | INT (0: 남성, 1: 여성)                                | 모델 학습용으로 int 변환                             |
| price_preference  | INT (1~5)                                             | 선호 가격대                                          |
| spicy_preference  | INT (1~5)                                             | 매운 음식 선호도                                     |
| calorie_preference| INT (1~5)                                             | 칼로리 고려 정도                                     |
| preferred_category| INT (1: 한식, 2: 중식, 3: 양식, 4: 일식, 5: 기타)      | 선호 음식 종류                                       |
| newness_preference| BOOLEAN (0 또는 1)                                    | 새로움 선호 여부 (0: 먹던 것 위주 / 1: 새 음식 선호)   |


## Food Table(Item)
| 컬럼명      | 타입                                                   | 설명                                                |
|------------|------------------------------------------------------|---------------------------------------------------|
| food_id    | INT (PK)                                              | 음식 고유 ID                                         |
| name       | VARCHAR(20)                                           | 음식 이름 (참고용, 학습 시 제외 가능)                  |
| category   | INT (1: 한식, 2: 중식, 3: 양식, 4: 일식, 5: 기타)      | 음식 종류                                           |
| price_level| INT (1~5)                                             | 가격대                                              |
| spicy_level| INT (1~5)                                             | 매운 정도                                           |
| popularity | INT (1~5)                                             | 대중성 (많이 찾는 정도)                              |
| calorie    | INT (대략 kcal)                                       | 칼로리 수치                                         |
| is_trendy  | BOOLEAN (0 or 1)                                      | 요즘 인기 음식 여부 (트렌디함)                        |


## Interaction Table
| 컬럼명         | 타입                         | 설명                              |
|----------------|----------------------------|---------------------------------|
| interaction_id | INT (AUTO_INCREMENT, PK)   | Interaction 고유 ID               |
| user_id        | INT                        | user 테이블 참조 (FK)              |
| food_id        | INT                        | food 테이블 참조 (FK)              |
| satisfaction   | INT                        | 1~5 만족도 점수 (학습 target)       |



