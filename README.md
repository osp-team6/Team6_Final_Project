### 가상환경 (venv)

```shell
# 가상환경 생성
$ python3 -m venv .venv

# 가상환경 활성화 (환경별로 상이)
$ source .venv/bin/activate #bash/zsh	
$ source .venv/bin/activate.csh #csh/tcsh
$ .venv/bin/Activate.ps1 #PowerShell Core	
PS C:\> .venv\Scripts\Activate.ps1 #PowerShell
C:\> .venv\Scripts\activate.bat #cmd.exe	

# pip install (pip설치되어 있다면 생략, pip or pip3를 타이핑시 실행 안될 경우)
https://foreverhappiness.tistory.com/67

# requirement 설치
pip install requirements.txt

#pip freeze > requirements.txt #다른 패키지 설치후 requirements 갱신
```


# 데이터베이스 (DataBase)
### create database and table 
```shell
$ sudo systemctl start postgresql.service
$ sudo -u postgres createuser --interactive
$ sudo -u postgres createdb team6
$ sudo adduser team6
$ sudo -u team6 psql
$ CREATE table history ( id INT, ts varchar(16), topic VARCHAR(30), prob NUMERIC(4,3))
```
### DB Class
- insertDB(table, data)
    - table : table명
    - data : [id,timestamp,topic,probability] list form
- readDB(table, topic)
    - table : table명
    - topic : 입력한 topic
    - return [timestamp, probability] list form
- db = psycopg2.connect(host='localhost', dbname='team6',user='team6',password='team6',port=5432)

### Table
- HISTORY ( id INT, ts varchar(16), topic VARCHAR(30), prob NUMERIC(4,3) )
    - has history of topics
    - id : assign in input order
    - topic : input topic
    - prob : positive probability of topic ( negative probability = 1 - prob)
 
