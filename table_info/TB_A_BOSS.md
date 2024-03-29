# Entity
```java
// 관리자_기준정보 보스 테이블
@Table(name = "TB_A_BOSS")
@Data
@Entity
@NoArgsConstructor
@AllArgsConstructor
@Builder
@Accessors(chain = true)
public class Boss {

    // id
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @JsonProperty("id")
    private Long id;

    // 보스이름
    @JsonProperty("name")
    private String name;

    // 생성자
    @JsonProperty("created_by")
    private String createdBy;

    // 생성일
    @JsonProperty("created_dt")
    private LocalDateTime createdDt;

    // 변경자
    @JsonProperty("updated_by")
    private String updatedBy;

    // 변경일
    @JsonProperty("updated_dt")
    private LocalDateTime updatedDt;
    
    @OneToMany(fetch = FetchType.LAZY, mappedBy = "boss")
    private List<BossDetail> BossDetailList;
    
}
```

# DB
```sql
CREATE TABLE TB_A_BOSS
(
    `id`          BIGINT         NOT NULL    AUTO_INCREMENT COMMENT 'id', 
    `name`        VARCHAR(20)    NULL        COMMENT '보스이름', 
    `created_by`  VARCHAR(30)    NULL        COMMENT '생성자', 
    `created_dt`  DATETIME       NULL        COMMENT '생성일', 
    `updated_by`  VARCHAR(30)    NULL        COMMENT '변경자', 
    `updated_dt`  DATETIME       NULL        COMMENT '변경일', 
    CONSTRAINT  PRIMARY KEY (id)
)ENGINE = InnoDB DEFAULT CHARACTER SET = utf8mb4 COLLATE = utf8mb4_bin;

ALTER TABLE TB_A_BOSS COMMENT '보스';
```

> ![image](https://user-images.githubusercontent.com/17442343/120921713-de17e480-c6ff-11eb-9553-0cad6e900d3e.png)

## 확인용 쿼리
```sql
select A.name, b.name, b.day_div, c.pay
from TB_A_BOSS a
	,TB_A_BOSS_LEVEL b
    ,TB_A_BOSS_PAY c
where a.id = b.boss_id
  and a.id = c.boss_id
  and b.id = c.level_id
  and c.id = b.pay_id
```
> ![image](https://user-images.githubusercontent.com/17442343/120922613-21c11d00-c705-11eb-8e3d-8fa8283c6d7e.png)
