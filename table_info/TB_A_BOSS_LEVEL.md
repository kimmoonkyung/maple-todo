# Entity
```java
// 관리자_기준정보 보스 난이도
@Table(name = "TB_A_BOSS_LEVEL")
@Data
@Entity
@NoArgsConstructor
@AllArgsConstructor
@Builder
@Accessors(chain = true)
public class BossLevel {

    // id
    @JsonProperty("id")
    private Long id;

    // 난이도
    @JsonProperty("cd")
    private String cd;

    // 난이도명
    @JsonProperty("name")
    private String name;
    
    // 클리어구분
    @JsonProperty("day_div")
    private String dayDiv;

    // 생성자
    @JsonProperty("created_by")
    private String createdBy;

    // 생성일
    @JsonProperty("created_dt")
    private Timestamp createdDt;

    // 변경자
    @JsonProperty("updated_by")
    private String updatedBy;

    // 변경일
    @JsonProperty("updated_dt")
    private Timestamp updatedDt;

    // 보스ID
    @ManyToOne
    private Boss boss;
    
    // 결정석ID
    @OneToOne(mappedBy = "bossLevel")
    private Pay pay;
    

}
```

# DB
```sql
CREATE TABLE TB_A_BOSS_LEVEL
(
    `id`          BIGINT         NOT NULL    AUTO_INCREMENT COMMENT 'id', 
    `cd`          VARCHAR(2)     NULL        COMMENT '난이도', 
    `name`        VARCHAR(10)    NULL        COMMENT '난이도명', 
    `day_div`     VARCHAR(2)     NULL        COMMENT '클리어구분', 
    `created_by`  VARCHAR(30)    NULL        COMMENT '생성자', 
    `created_dt`  DATETIME       NULL        COMMENT '생성일', 
    `updated_by`  VARCHAR(30)    NULL        COMMENT '변경자', 
    `updated_dt`  DATETIME       NULL        COMMENT '변경일', 
    `boss_id`     BIGINT         NOT NULL    COMMENT '보스ID', 
    `pay_id`      BIGINT         NULL        COMMENT '결정석ID', 
    CONSTRAINT  PRIMARY KEY (id)
)ENGINE = InnoDB DEFAULT CHARACTER SET = utf8mb4 COLLATE = utf8mb4_bin;

ALTER TABLE TB_A_BOSS_LEVEL COMMENT '보스 난이도';


> 
