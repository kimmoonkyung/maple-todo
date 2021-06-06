
```
이력 테이블은 관리자 화면에서
Insert나 Update, Delete를 실행 했을 때,
DB 트리거를 활용하여 이력 테이블에 Insert 되도록 한다.

이력에 어떤 내용을 Insert 할 것인지 좀 더 고민 해봐야 함.
```

# DB
```sql
CREATE TABLE TB_A_INFO_HST
(
    CD_GROUP_ID    VARCHAR2(20)    NOT NULL, 
    CD             VARCHAR2(20)    NOT NULL, 
    CD_NM          VARCHAR2(20)    NOT NULL, 
    RFRN_1         VARCHAR2(20)    NULL, 
    RFRN_2         VARCHAR2(20)    NULL, 
    RFRN_3         VARCHAR2(20)    NULL, 
    CREATE_ID      VARCHAR2(20)    NOT NULL, 
    CREATE_DT      DATE            NOT NULL, 
    UPDATE_ID      VARCHAR2(20)    NOT NULL, 
    UPDATE_DT      DATE            NOT NULL, 
    HST_DT         VARCHAR2(8)     NOT NULL, 
    CONSTRAINT PK_MW_CD_HST PRIMARY KEY (CD_GROUP_ID)
)
;

COMMENT ON TABLE TB_A_INFO_HST IS '코드 변경 이력'
;

COMMENT ON COLUMN TB_A_INFO_HST.CD_GROUP_ID IS '코드그룹'
;

COMMENT ON COLUMN TB_A_INFO_HST.CD IS '코드'
;

COMMENT ON COLUMN TB_A_INFO_HST.CD_NM IS '코드명'
;

COMMENT ON COLUMN TB_A_INFO_HST.RFRN_1 IS '참고1'
;

COMMENT ON COLUMN TB_A_INFO_HST.RFRN_2 IS '참고2'
;

COMMENT ON COLUMN TB_A_INFO_HST.RFRN_3 IS '참고3'
;

COMMENT ON COLUMN TB_A_INFO_HST.CREATE_ID IS '생성자'
;

COMMENT ON COLUMN TB_A_INFO_HST.CREATE_DT IS '생성일'
;

COMMENT ON COLUMN TB_A_INFO_HST.UPDATE_ID IS '변경자'
;

COMMENT ON COLUMN TB_A_INFO_HST.UPDATE_DT IS '변경일'
;

COMMENT ON COLUMN TB_A_INFO_HST.HST_DT IS '변경이력일'
;
```

> ![image](https://user-images.githubusercontent.com/17442343/120919431-8162fc80-c6f4-11eb-9581-1e01735c7804.png)

