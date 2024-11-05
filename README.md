창의공학설계 과제 계획서 팀03 / 
조장: 배각경 / 
팀원: 박기범, 지승현, 김영우, 김채환 / 

1. 연구배경 및 필요성(중요성)
자동차 급발진 사고는 매년 평균적으로 30~50건정도로 꽤 빈번히 일어나는 사고이다.
국립과학수사원은 이에 대해 조사를 착수, 최근 5년간의 급발진 의심 사고(364건)를 조사한 결과,
분석이 불가능한 일부 사례를 제외하고 주된 원인은 모두 ‘페달 오인’이었다.
(참고 기사: https://newautopost.co.kr/issue-plus/article/123221/)
최근 강릉에서 급발진 사고가 발생했다. 운전자는 이 사고 때문에 12살 된 손자를 잃었다. 
만약 해당 사고에서 자동차의 명확한 급발진 방지책이 있었다면, 이러한 비극은 일어나지 않았을 것이다.
이러한 사고를 방지하기 위해, 페달의 종류를 시각적으로 확인할 수 있는 장치가 필요하다.

 한편, 급발진 사고는 그 발생 이유를 명확히 밝히는 데 어려움이 있다.
현재 사용중인 EDR(event data recoder)은 충돌 전후로  5초간의 데이터만 기록하기 때문에, 전체적인 사고 맥락의 파악이 힘들다는 문제점이 있다. 
또한 EDR은 일반 운전자나 법률전문가가 해석하기 어려워, 제조사의 데이터 제공에 기대야만 한다. 
이는 제조사에 의해 데이터 접근이 제한되거나 해석 과정에서의 왜곡될 가능성이 있다. 
위와 같은 문제로 이 연구를 진행, ‘페달 오인 방지 및 사고증명 장치’를 제작한다.

2. 관련기술의 현황
  자동차 급발진 감지 및 페달 감지 기술은 소프트 웨어, 자동차 안전 시스템의 발전에 
힘 입어 지속적으로 개선되고 있다.
 이러한 기술들은 차량의 안전성을 높이고, 사고를 예방하는 데 중요한 역할을 하고 있다.
페달 오조작 방지 장치의 경우, 한국교통안전공단은 이 기술의 개발 및 평가를 진행 중이며,
일본에서는 이미 차량의 93%에 해당 장치가 도입된 상황이다. 이를 통해 페달 오조작 사고로 인한 인명 피해를 효과적으로 줄이고 있다.
(참고 기사: https://it.chosun.com/news/articleView.html?idxno=2023092119030 )

3. 기대효과 및 활용
사용하던 차량에 부착 가능한 점에서 실효성이 높다.
 운전자는 본인이 밟은 페달에 대한 명확한 구분이 가능해 진다. 
따라서 페달 오인 급가속 사고 방지에 큰 도움이 된다.
이전에는 제조사와 운전자의 엇갈리는 의견이 있었지만 (제동 페달 작동 기록이 남았더라도 페달을 ‘충분히 강하게 밟지 않았다’고 주장하면 반박할 길이 없었다)
제동 페달에 가해진 압력이 기록되면 브레이크 작동 여부에 대한 논란이 사그라질 가능성이 크다

4. 목표
  1. 자동차의 각각의 페달에 압력센서 부착
  2. 압력 센서에 가해진 압력의 정도를 측정 및 기록
        2-1 (사고 방지 목적) 압력센서에 압력이 가해질 시, 각각의 심볼이나 문자를 LCD모듈을 통해 출력
        2-2 (사고 증명 목적) 압력센서에 가해진 압력을 시간대별로 기록해, 누구나 보기 
           쉽도록 설계함.
  3. 법률전문가나 일반 운전자가 확인하기 쉽게 설계해, 제조사 종속성을 줄인다.

5. 내용
-압력 페달 센서 장치 설계 및 제작
-압력 페달 센서 장치 소프트웨어 설계
-운전 중 압력 수치를 저장할 수 있는 sd카드 소켓 연결
-압력 페달 센서 장치 실험(sd카드에 오류 없이 저장이 되는지,lcd에 출력되어야하는 
 내용들이 나오는지, 압력의 세기에 알맞게 압력 수치가 기록되는지 등)

<SD소캣>
![image](https://github.com/user-attachments/assets/80636f1d-42cb-48a0-9af8-1273e1f42f43)

<LCD>
![image](https://github.com/user-attachments/assets/300a6c21-49b4-40d1-84e9-41f9d3823e3f)

6. 구현 방법
(1) 필요한 부품
● Arduino Mega (아두이노 메가)
● FSR402 압력센서
● SD카드 리더기 MPL115A2
● DS3231 RTC Modue 시계 모듈
● SD카드 4GB
● 브레드보드
● 점퍼케이블
● LCD 모듈 20 x 4
● 전원 공급장치

(2) 회로 구성 설명
FSR-402 압력 센서
FSR 센서의 한쪽 단자: Arduino Mega의 A0,A1  핀에 연결
FSR 센서의 다른 단자: GND에 연결
SD 카드 모듈
CS 핀: Arduino Mega의 디지털4번 핀에 연결
MOSI 핀: Arduino Mega의  51번 핀에 연결
MISO 핀: Arduino Mega의  50번 핀에 연결
SCK 핀: Arduino Mega의  52번 핀에 연결
VCC 핀: 5V에 연결
GND 핀: GND에 연결
DS3231 RTC 모듈
VCC 핀: 5V에 연결
GND 핀: GND에 연결
SDA 핀: Arduino Mega의  20번 핀에 연결
SCL 핀: Arduino Mega의  21번 핀에 연결
