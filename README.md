# everytime_subject_review_crawler
로그인된 상태에서 에브리타임 강의평가를 keyword='과목명'을 입력하고 실행시 자동으로 CSV 파일로 강의평가를 추출하는 도구입니다.
첨부한 파일에는
1. 자동 크롤러(auto crawler.ipynb) : 로그인 및 과목명 만 입력 시 자동으로 과목명_parsed_articles.csv이름의 파일로 정리됩니다
2. 수동 작업(manual articles html parser.ipynb) : 로그인 후 과목명, 교수명, 강의평 html 입력 시 과목명_parsed_articles.csv이름의 파일로 정리됩니다.
3. 수동 작업 후 실행하는 파일 (csv header cleaner.ipynb) : 수동 작업 시 같은 과목이지만 교수가 다를 경우 csv 헤더가 중복되는 문제가 생기는데, 이를 수정하기 위한 코드입니다. 실행 시 코드와 같은 폴더에 있는 과목명_parsed_articles.csv 파일로부터 과목명_cleaned_articles.csv을 모두 생성하고 cleaned_files 폴더에 저장합니다.


위 ipynb 파일은 windows 10 64bit visual studio code로 작업하였고, 
1의 자동 크롤러 파일은 구글 colab 등과 같은 타 환경에서는 호환되지 않습니다. 
대신 colab에서 2,3의 수동 작업 파일은 실행 가능합니다.
작업을 하실 때 chrome webdriver가 필요하므로 첨부된 폴더 내의 파일 자체를 그대로 활용하시거나 호환성이 맞지 않는다면 https://developer.chrome.com/docs/chromedriver/downloads?hl=ko 여기 들어가셔서 코드가 포함된 폴더에 압축을 푸셔야 제대로 작동될 것입니다.


또한 selinium, openpyxl, pandas, beautifulsoup 패키지를 사전에 설치하셔야 합니다.

자동 크롤러 및 수동 작업을 이용하기 위해서는 에브리타임 계정이 있어야만 합니다. 최대한 차단을 피하기 위하여 작동 속도를 늦췄고 webdriver을 웹사이트에서 인식하지 못하도록 하는 코드를 삽입했습니다. 그렇지만 자동 크롤러를 반복해서 작동할 경우, 웹 사이트에서 로봇으로 인식해서 계정을 영구 차단 할 수 있으므로, 로그인을 한 뒤에 과목을 하나만 정해서 시간을 두고 주의해서 사용해주시면 감사하겠습니다.

작동하는 중간에는 창을 최소화하고 다른 작업을 해도 상관은 없으나, 자동으로 열리는 탭을 임의로 닫거나 하면 작동이 멈출 수 있습니다.
