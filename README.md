# Read me
Smart policing based on the analysis of big data ensures the development and sustainability of police policy. 
However, it is difficult to find instances in which the results of data analysis have been applied to actual policy in the field of crime prevention. 
The South Korean police force recognizes the need for smart policing and is engaged in various research and field support activities. 
Some examples that are especially relevant for crime investigation include analyzing the connections between cases and predicting the location of the next crime in a series of crimes and the location of suspects. 
However, it is difficult to find examples of police policy that use big data. 
Therefore, this study aims to suggest a model that uses big data to respond to emergency calls efficiently. 
First, we extract hotspots that are predicted to be locations of criminal activity based on an analysis of the association between community environment data and crime data. 
Second, we create a route having the shortest travel time to the crime location by developing a route optimization algorithm. 
Lastly, we assess the performance of the patrol routes in reflecting real-time traffic information. 
If the data application model suggested in this study could be adjusted and applied to the current police patrol system, the model could be used by each police department effectively.

## Heatmap extraction (ipython)
* About this code
  * 범죄 데이터 및 공공 데이터의 상관관계를 분석 및 제안하는 범죄 위험도 값 산출 방법을 통해 각 grid 별 범죄 위험도 산출
* 실행 환경
  * Ubuntu - Jupyter notebook, Mysql이 설치 필요 
* Input data
  * Crime & comemrcial data - dataframe 양식은 논문 참조
  * Grid image file - 순찰 경로를 형성하고자 하는 지역의 grid image file
* Output data
  * overall_local_heatmap_arr.npy - 전체 케이스의 각 grid별로 산출된 범죄 위험도가 저장된 배열 데이터 파일
 
## Route generation (python)
* About this code
  * 산출된 grid 별 범죄 위험도 값을 기반으로 hotspot 추출 및 최적 순찰 경로 생성
* 실행 환경
  * Python 실행이 가능한 모든 OS
  * main.py source code 실행
* Input data
  * overall_local_heatmap_arr.npy - Heatmap extraction source의 output
  * Grid image file - 순찰 경로를 형성하고자 하는 지역의 grid image file
* Output data
  * 최적 순찰 경로의 '위도', '경도' 좌표
