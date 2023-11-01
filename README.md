# Dishwashers_Anomaly_Detection


## 문제 정의
▶ 삼천 산업에서 생산되는 식기세척기의 용착 불량 제품 문제
 
## 기대효과
▶ 사전 이상징후 감지 및 점검을 통해 불량품 처리 개선 

## 해결 방안
▶ 데이터 기반으로 이상징후를 정의, 전력 데이터 모니터링을 통해 이상징후 포착 및 실시간 점검 <br>
▶ 불량품이 발생하기 전 이상 증상에 대한 정의  <br>
▶ 가설 수립 및 검증<br>
▶ 이상 탐지 모델링 수행<br>
 
## 성과측정
 ▶ 모델의 성능 지표를 활용  
 
## 현업적용
▶ 결과 데이터 대시보드 및 BI 시스템에 출력 및 모니터링
 
## 발전
▶ 실시간 측정 데이터 수집 및 DB 적재 시스템 구축 

## 결론
▶ lstm auto encoder로 가중치의 정도를 어느정도로 할지 추정함 <br>
▶ lstm을 통해 window size 이후의 값 predict <br>
▶ 10개의 anomaly 지점을 graph 분석을 해본 결과 정상 지점에 비해 peak의 값(value)과 width가 상대적으로 낮게 나와 이를 바탕으로 발전시키면 좋을 거 같다.


## 추가적으로 보완했으면 좋았을 부분 
▶ 시간 도메인에서 이상 구간을 식별하고 해당 부분의 데이터를 분리 <br>
▶ 분리한 이상 구간에 대해 푸리에 변환을 수행합니다. 이 작업을 통해 해당 이상 부분이 어떤 주파수 성분으로 표현되는지 확인할 수 있습니다.<br>
▶ 푸리에 변환 결과에서 주파수 성분의 크기 또는 진폭 정보를 살펴봅니다. 낮은 진폭을 갖는 주파수 성분을 확인하면 이상 구간이 주파수 도메인에서 어떤 주파수 영역에 해당하는지 알 수 있습니다.<br>
▶ 이를 통해 구체적인 이상 신호를 탐지


<br>
Spectral Residual <br>
- FFT로 로그 스펙트럼 변환을 수행한 후 <br>
- Spectral Residual 절차를 거친 후 <br>
- 도출된 변환 스펙트럼을 다시 역FFT로 원래 데이터로 돌린다. <br>
 [자료](https://velog.io/@jsshin2022/Paper-Review-Time-Series-Anomaly-Detection-Service-at-Microsoft)
![image](https://github.com/ru2zi/PdM-Dishwashers_Anomaly_Detection/assets/91187038/3bfac259-37ab-4af6-8fb9-55921a59e78e)


<br>
SR-CNN <br>
Spectral-Residual을 일종의 전처리기로 활용한 후, 이상 지점이 도드라진 데이터에 대하여 CNN을 적용하여 이상이 있는 지점을 판별하는 이상 감지기로 활용
