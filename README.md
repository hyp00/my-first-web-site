# HobHub : AI 기반 맞춤형 취미 추천 및 아카이빙 웹 서비스
사용자가 가진 조건(나이, 성별, 여가시간, 소득, 거주 지역)을 종합적으로 고려해 AI를 기반으로 사용자에게 최적인 취미를 추천함으로써 사용자들이 간편하고 빠르게 취미 활동을 시작할 수 있도록 도와주는 웹 서비스

![logo](https://github.com/money-catcher/HobHub-Front/assets/109021332/3859f1d4-beb4-42fc-8081-9004cf2b0dd2)

## 팀원 소개
| <img src="https://avatars.githubusercontent.com/u/108976815?v=4" width="200px" /> | <img src="https://avatars.githubusercontent.com/u/104544503?v=4" width="200px" /> | <img src="https://avatars.githubusercontent.com/u/109021332?v=4" width="200px" />  |
| :------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: |
|                      [박유진](https://github.com/jin171)                       |                        [박혜진](https://github.com/hyp00)                        |                     [최예빈](https://github.com/beenvyn)                      |       
|                   팀장, 백엔드                |                   팀원, 백엔드             |        팀원, 프론트엔드           |          

## 기술 스택
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"> 
<img src="https://img.shields.io/badge/Pandas-150458?style=flat square&logo=pandas&logoColor=white"> 
<img src="https://img.shields.io/badge/Numpy-013243?style=flat-square&logo=numpy&logoColor=white"> 
<img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white">
<img src="https://img.shields.io/badge/Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white">

## 라이브러리
`````
        "pandas": "^1.4.2",
        "numpy": "^1.22.3",
        "flask": "^2.1.1",
        "pytest": "^7.1.2",
        "flask_cors": "^3.0.10",
        "requests": "^2.28.1",
        "openpyxl": "^3.0.9"
``````
## 데이터
콘텐츠 기반 추천 알고리즘에 사용된 데이터: <br>
https://docs.google.com/spreadsheets/d/1leFDaOCDJfxu9AZgyfMM_50xPK2Z39ayGna_stVtbxw/edit?gid=1227239017#gid=1227239017  <br>
[출처: 컨슈머인사이트 'MZ 문화여가활동 특징 데이터']

우선순위 반환하는데 사용된 데이터: <br>
https://docs.google.com/spreadsheets/d/1iDMAPNro1aABKKqTNvgXG0qRIvMug79l/edit?usp=drive_link&ouid=112129444307325997977&rtpof=true&sd=true  <br>
[출처: 컨슈머인사이트 'MZ 문화여가활동 특징 데이터']

협업 필터링 추천 알고리즘에 사용된 데이터: <br>
https://docs.google.com/spreadsheets/d/1Fb4xSgideUwhk5jMRLWG8XCmubvU8s1Y/edit?gid=1062421834#gid=1062421834  <br>

# 프로젝트 구조도 및 설명
## 프로젝트 구조도
````
🌟src
📂Flask
├─ 📄app.py
├─ 📄chatbot.py
├─ 📄file.py
├─ 📄hobby3 _new.csv
├─ 📄hobby3사본.xlsx
├─ 📄merged_hobbies_complete.xlsx
├─ 📄private_key.json
````
## 폴더별 설명
- `📂app.py` : 프로젝트의 메인 애플리케이션 파일로, Flask 애플리케이션 인스턴스를 생성하고 구성하며, 주요 라우팅을 설정하여 다양한 URL 경로에 대해 다른 기능을 호출하고, 서버를 실행하여 클라이언트 요청을 처리함.
- `📄chatbot.py` : 챗봇 기능을 구현하는 파일. 사용자 입력을 받아 분석하고, 자연어 처리(NLP) 기술을 활용하여 사용자의 의도를 파악한 후, 파악된 의도에 따라 적절한 응답을 생성함. Flask 라우트를 통해 웹 인터페이스로 챗봇 서비스를 제공함.
- `📄file.py` : 파일 입출력과 관련된 유틸리티 함수들이 포함된 파일. CSV 파일과 Excel 파일(.xlsx)을 읽고 쓰는 기능을 제공하며, 데이터를 특정 형식으로 변환하거나 처리하는 유틸리티 함수를 포함.
- `📄hobby3 _new.csv` : 콘테츠 기반 알고리즘에 활용되는 데이터 파일
- `📄hobby3사본.xlsx` : 피드백 받은 뒤 우선순위 반환하는데 활용되는 데이터 파일
- `📄merged_hobbies_complete.xlsx` : 사용자 기반 협업필터링 알고리즘에 활용되는 데이터 파일

## 실행 방법
1. AWS EC2 인스턴스 생성한 뒤, 생성된 EC2 인스턴스에 SSH로 접속
2. EC2 인스턴스에 필요한 패키지 설치
````
sudo yum update -y
sudo yum install git -y
sudo yum install python3 -y
sudo yum install python3-pip -y
````
3. 프로젝트 클론
````
git clone https://github.com/money-catcher/Flask.git
cd Flask
````
4. 가상 환경 설정
```
python3 -m venv venv
source venv/bin/activate
```````
5. 프로젝트에 필요한 패키지 설치
````
python3 -m venv venv
source venv/bin/activate
````
6. Flask 애플리케이션 실행
````
flask run --host=0.0.0.0 --port=80 &
````
