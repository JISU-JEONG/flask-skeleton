# Flask-Skeleton Korean ver.
## 개요
- 기본 CRUD 기능을 제공하는 API Code입니다

* Dir 구조
```
├── app.py
├── bin
│   ├── run_server.sh
│   ├── test.sh
│   ├── init_db.sh
│   ├── migrade_db.sh
│   ├── upgrade_db.sh
│   └── downgrade_db.sh
├── main
│   ├── __init__.py
│   ├── controllers
│   │   ├── __init__.py
│   │   ├── common.py
│   │   ├── board.py
│   │   └── comment.py
│   ├── flask_skeleton.cfg
│   ├── flask_skeleton.default.cfg
│   ├── models
│   │   ├── __init__.py
│   │   ├── common
│   │   │   ├── base.py
│   │   │   └── error.py
│   │   ├── board.py
│   │   └── comment.py
│   └── schema
│       ├── __init__.py
│       ├── board.py
│       └── comment.py
├── requirements.txt
├── run.py
├── migrate.py
└── test
     ├── __init__.py
     ├── conftest.py
     ├── helpers.py
     └── test_api.py
```

## 설치 방법
- 의존성 설치
```
python3 -m pip install -r requirements.txt
```
- cfg 구성(위치 /main/default.cfg)
```
SCHEMA_TEST="schema_name"
SQLALCHEMY_DATABASE_URI="postgresql+psycopg2://user_name:pw_name@localhost:5432/db_name"
```
- Database 를 PostgreSQL 로 가정하고 구성하였습니다. 다른 데이터베이스를 사용시 requirements.txt 및 flask_skeleton.default.cfg 의 URI 를 변경해야 합니다.

## 설정 파일 복사
`cp main/flask_skeleton.default.cfg main/flask_skeleton.cfg`

## API 실행 방법
`./bin/run_server.sh {port 번호}`

## Swagger endpoint
`/docs`

## DB 세팅
### init db
- 처음 프로젝트 실행시 실행해 줍니다.
`./bin/init_db.sh`

### migrate db
- 모델에 수정 사항이 있을시 마이그레이트를 실행해 줍니다.
`./bin/migrate_db.sh`

### upgrade db
- 모델에 수정 사항을 db에 업그레이드해 줍니다.
`./bin/upgrade_db.sh`

### downgrade db
- 모델에 기존 수정 사항을 다운그래이드해 줍니다.
`./bin/downgrade_db.sh`

## test 방법
`./bin/test.sh`
