# Entity
```java
// 기준정보 기준정보
@Table(name = "TB_A_INFO")
@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class Info {

    // 코드그룹
    @JsonProperty("cd_group_id")
    private String cdGroupId;

    // 코드
    @JsonProperty("cd")
    private String cd;

    // 코드명
    @JsonProperty("cd_nm")
    private String cdNm;

    // 참고1
    @JsonProperty("rfrn_1")
    private String rfrn1;

    // 참고2
    @JsonProperty("rfrn_2")
    private String rfrn2;

    // 참고3
    @JsonProperty("rfrn_3")
    private String rfrn3;

    // 생성자
    @JsonProperty("create_id")
    private String createId;

    // 생성일
    @JsonProperty("create_dt")
    private LocalDateTime createDt;

    // 변경자
    @JsonProperty("update_id")
    private String updateId;

    // 변경일
    @JsonProperty("update_dt")
    private LocalDateTime updateDt;

}
```

# DB 
```sql
CREATE TABLE TB_A_INFO
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
    CONSTRAINT PK_MW_CD PRIMARY KEY (CD_GROUP_ID)
)
;

COMMENT ON TABLE TB_A_INFO IS '기준정보';

COMMENT ON COLUMN TB_A_INFO.CD_GROUP_ID IS '코드그룹';

COMMENT ON COLUMN TB_A_INFO.CD IS '코드';

COMMENT ON COLUMN TB_A_INFO.CD_NM IS '코드명';

COMMENT ON COLUMN TB_A_INFO.RFRN_1 IS '참고1';

COMMENT ON COLUMN TB_A_INFO.RFRN_2 IS '참고2';

COMMENT ON COLUMN TB_A_INFO.RFRN_3 IS '참고3';

COMMENT ON COLUMN TB_A_INFO.CREATE_ID IS '생성자';

COMMENT ON COLUMN TB_A_INFO.CREATE_DT IS '생성일';

COMMENT ON COLUMN TB_A_INFO.UPDATE_ID IS '변경자';

COMMENT ON COLUMN TB_A_INFO.UPDATE_DT IS '변경일';
```
> ![image](https://user-images.githubusercontent.com/17442343/120919061-9fc7f880-c6f2-11eb-817f-57f07a2757c3.png)
