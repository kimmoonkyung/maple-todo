# Entity
```java
// 관리자_기준정보 보스 보상(결정석)
@Table(name = "TB_A_BOSS_PAY")
@Data
@Entity
@NoArgsConstructor
@AllArgsConstructor
@Builder
@Accessors(chain = true)
public class BossPay {

    // id
    @JsonProperty("id")
    private Long id;

    // 결정석가격
    @JsonProperty("pay")
    private Integer pay;

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

    // 난이도ID
    @JsonProperty("level_id")
    private Long levelId;
    
    // 보스ID
    @ManyToOne
    private Boss boss;
    
    // 난이도ID
    @OneToOne(mappedBy = "bossPay")
    private BossLevel bossLevel;

}
```

# DB
```sql
CREATE TABLE TB_A_BOSS_PAY
(
    `id`          BIGINT         NOT NULL    AUTO_INCREMENT COMMENT 'id', 
    `pay`         INT            NULL        COMMENT '결정석가격', 
    `created_by`  VARCHAR(30)    NULL        COMMENT '생성자', 
    `created_dt`  DATETIME       NULL        COMMENT '생성일', 
    `updated_by`  VARCHAR(30)    NULL        COMMENT '변경자', 
    `updated_dt`  DATETIME       NULL        COMMENT '변경일', 
    `boss_id`     BIGINT         NULL        COMMENT '보스ID', 
    `level_id`    BIGINT         NULL        COMMENT '난이도ID', 
    CONSTRAINT  PRIMARY KEY (id)
)ENGINE = InnoDB DEFAULT CHARACTER SET = utf8mb4 COLLATE = utf8mb4_bin;

ALTER TABLE TB_A_BOSS_PAY COMMENT '보스 보상(결정석)';

```

> 
