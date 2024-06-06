# GURU 게임 추천 시스템

## 프로젝트 개요
GURU는 사용자들에게 맞춤형 게임 추천을 제공하기 위해 설계된 시스템입니다. 다양한 게임 데이터베이스를 활용하여 사용자들이 선호하는 게임을 쉽게 찾을 수 있도록 돕습니다.

## 프로젝트 배경
게임 산업은 최근 몇 년간 급격히 성장하며 수많은 게임이 출시되고 있습니다. 수천 개의 게임 중에서 자신에게 맞는 게임을 찾는 일은 매우 어려운 과제가 되었습니다. 이는 사용자들이 원하는 게임을 쉽게 찾을 수 있도록 돕는 게임 추천 시스템의 필요성을 증대시켰습니다. 이러한 배경에서 GURU 게임 추천 시스템을 개발하게 되었습니다.

## 프로젝트 목적
GURU의 주요 목적은 사용자 개개인의 취향과 게임 접근성을 개선하는 것입니다. 이를 통해 사용자가 다양한 게임에 더 쉽게 접근하고 자신에게 맞는 게임을 추천받아 더욱 만족스러운 게이밍 경험을 할 수 있도록 돕는 것입니다.

## 데이터 출처 및 전처리 과정
GURU 프로젝트는 다음과 같은 데이터 출처를 사용하였습니다:
- **RAWG**: 다양한 장르와 플랫폼의 게임을 포괄하는 방대한 데이터베이스.
- **IGDB**: 게임에 대한 상세한 메타데이터를 제공하여 다양한 기준으로 추천 가능.

### 데이터 전처리 과정
1. Metacritic 제거
2. description, background_image, website: 빈 문자열로 채움
3. background_image: 이미지 없음 URL로 채움
4. added_by_status: 'yet', 'owned', 'beaten', 'toplay', 'dropped', 'playing’ 나눈 후 나머지는 0으로 채움
5. 데이터 매핑: 크롤링 데이터 및 Kaggle 데이터로 결측치가 있는 데이터를 이름으로 매핑하여 결측치 채움
6. Demo, Test, Prototype 등 이름이 들어간 게임 제거
7. 추가 크롤링: 결측치가 있는 데이터만 별도로 크롤링하여 데이터 채움
8. 빈 문자열 처리: 시간상의 제약으로 인해 채울 수 없는 데이터는 빈 문자열로 대체
9. 데이터 형식 변경: 추천 시스템을 개발하는 데이터가 IGDB이기 때문에 RAWG 형식을 IGDB에 맞춰 변경

## 시스템 아키텍처

### 프론트엔드
- **index.html**: 웹 페이지의 구조와 콘텐츠를 정의.
- **styles.css**: 스타일을 정의하여 페이지의 시각적 요소를 결정.
- **scripts.js**: 동적 기능을 구현하여 사용자 상호작용을 처리.

### 백엔드
- **app.py**: 서버 애플리케이션을 설정하고 API 엔드포인트를 정의하여 클라이언트의 요청을 처리하고 데이터를 반환.
- **main.py**: 입력 받은 데이터를 사용자 취향에 맞게 추천된 게임 ID 반환.

## 추천 알고리즘 및 구현
추천 알고리즘은 사용자의 게임 플레이 기록과 선호도를 기반으로 합니다. 이를 위해 다양한 머신러닝 기법을 사용하여 정확한 추천을 제공합니다.

## 웹 구현
사용자가 쉽게 접근할 수 있는 웹 인터페이스를 제공하여 게임 추천 결과를 확인하고, 검색 및 필터링 기능을 사용할 수 있습니다.

## 결과 및 기대효과
- **사용자 맞춤형 게임 추천**: 사용자의 취향에 맞는 게임을 빠르고 정확하게 추천.
- **사용자 경험 향상**: 사용자가 적합한 게임을 쉽게 찾을 수 있도록 도와 게임 선택 시간을 절약.
- **게임 산업 발전 기여**: 더 많은 사용자가 다양한 게임을 경험할 수 있도록 도움.

## 사용된 아이콘 및 데이터 출처
- **아이콘 출처**: Freepik, Pixel perfect, rizal2109
- **데이터 출처**: RAWG, IGDB