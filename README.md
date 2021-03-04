오답노트 생성 홈페이지
OSS_AUTO_INCORRECT_NOTE: 
작성자: 장규범
2020년 6월 18일
진행: wix api를 사용하여 홈페이지 구성
https://jkb2221.wixsite.com/incorrect-note
오답노트 자동생성(LEET, psat, 자격증 시험(정보처리기사) 등 각종 시험 기출문제)

목적
시험 공부를 하다보면 틀린 문제를 한 곳에 모아서 다시 한 번 보거나 자주 틀리는 문제유형을 구분해서 보고 싶은 경우가 있다. 하나하나 손으로 문제 풀이한 것을 찾아볼 필요없이 OMR입력하는 것처럼 입력만 하면 답지에 의한 채점과 문제에 해당하는 카테고리끼리 묶어, 틀린문제들 모아서 시험지처럼 만들기(하나의 PDF), 해설서에 있는 답지 뒤에 붙여주는 기능을 제공하는 것이 목적이다.
목표
오답노트를 간단하고 편리하게 만들 수 있도록 각종 기능을 제공하는 것
기능
주요 시험의 기출 문제에 대한 자동채점
오답노트 자동생성
문제에 해당하는 카테고리 끼리 묶어서 생성
틀린 문제 전부 번호 오름차순으로 모아서 생성
시험문제 1개에 해당하는 것만이 아닌 시험 보고 난 뒤 틀린 문제
추가적으로 애매하거나 한 번 더 볼 필요성이 있는 문제들 
사진으로 찍어서 인식할 수 있는지 여부도 확인
난이도 별로 나누기
소제- 문제유형 별로 나누기

추가기능(있으면 좋고 없어도 괜찮은 기능)
문제집 사진 찍어서 웹 페이지에 올리면 pdf로 문제집 형식으로 구성되어 자동으로 만들어 지게 하는 기능
구현
wix API를 사용하여 홈페이지 구현, 각종 기능들은 추가적인 API를 통해서 구현할 예정, 파파고 API를 통해 라인을 통해 사진을 전송하면 사진 속 글자를 인식해서PDF파일에 포함할 수 있게 구현할 예정

프로젝트 개요
http://www.pxd.co.kr
웹페이지 만들기

흐름도
웹페이지 만들기
목록: PDF 변환, 오답노트 생성(카테고리 별 생성, 기출문제 연도별 생성, 각 난이도 별 생성), 데이터 제공(틀린 유형, 기출 문제별 점수, 난이도 별 틀린 문제)  
문제 데이터베이스 모으기
구글 클라우드 API 사용하여 각각의 공부하고 있는 것(리트, PSAT, 토익 문제 각각에 대해서 폴더로 구분되어 있고) 각각의 문제에 대한 PDF 업로드 되어서 클라우드에 있는 데이터를 홈페이지로 받기
홈페이지에서 어떤 과목의 몇 회 기출문제를 자동채점할 건지 생성
EX) 리트의 2019년도 기출문제 자동채점 누르면 -> OMR 자동채점으로 이동 
OMR 통한 자동채점 page
OMR 서식 들고와서 포인터로 선택 OR 그냥 번호에 맞게 서식 주고 쭉 넘어가게 Google form 형식으로 다음 누르면 
-> 자동채점되고 점수 출력, 유형별 , 난이도별, 
오답노트 구현 page
각 번호를 선정해서 오답노트로 만들어서 구현하는 것(OMR 자동채점 건너뛰고 자기가 원하는 것만 모아서 PDF로 만들기)
오답노트 서식에 번호 붙어서 합쳐서 PDF 파일로 저장
사진찍어서 PDF로 바꿀수 있게 구현(라인 또는 카카오 톡으로 보내면, 서버에서 받아서 웹페이지로 전송, 웹페이지에서 PDF 변환)


바로 프린트할 수 있게 구현할 수 있는지 여부 확인, 가능하면 구현


