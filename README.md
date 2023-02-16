# 💻Syllaverse 문제 파일 생성기

## 📍개발환경
- 언어 : Python
- 라이브러리 : beautifulsoup4, selenium, webdriver_manager

## 📍프로젝트 설명

교육중에 게시판에 올라오는 예제/실습 문제 파일을 만들기 번거로워서 만들기 시작했다.

예제문제와 실습문제가 둘 다 올라올 때도 있고 실습문제만 올라올 때가 있기 때문에

`element`가 없을 때를 `try except`문으로 감싸서 처리했다.

디렉토리 구조는 다음과 같다.

```bash
YYMMDD
├── 1_example
│   ├── 1000_문제이름.py
│   ├── 1001_문제이름.py
│   ├── ...
│   ├── input_1000.txt
│   ├── input_1001.txt
│   └── ...
└── 2_practice
    ├── 2000_문제이름.py
    ├── 2001_문제이름.py
    ├── ...
    ├── input_2000.txt
    ├── input_2001.txt
    └── ...
```

## 📍사용법

3가지 라이브러리를 설치한 후 

```Python
pip install beautifulsoup4
pip install selenium
pip install webdriver_manager
```

코드 내에 Email, PW에 본인의 아이디,비밀번호를 적어준다.
```Python
Email = 'ID'
PW = 'PW'
```

파일을 실행한다.

```Python
python syllaverse_file_generator.py
```



## 📍후기

개발 과정에서 `element`가 없을 때를 처리하는 과정에서 시간이 걸렸다.

```Python
status = driver.find_element(By.XPATH, "//span[contains(text(), '예제')]").click()
```
나는 해당 `element`가 있을 시 True를 받는것을 확인하고 없을 시 False를 받을거라고 생각해서

IF문으로 처리하려했지만

사실은 `NoSuchElementException` 에러를 받는거였다.

이 사실을 몰랐을 동안에 나는 단지 내 코드가 잘못된 줄 알았다.

다행히 구글링을 통해 에러를 받는다는 것을 확인하고 `try except` 구문으로 처리했다.

이 부분만 빼고는 수월하게 진행되었기 때문에 재밌게 개발했다.

해당 파일을 스터디 조원들에게 배포했는데 반응이 생각보다 좋아서 만족스러웠다.