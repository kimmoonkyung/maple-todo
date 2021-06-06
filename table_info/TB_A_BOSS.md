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
    private Timestamp createdDt;

    // 변경자
    @JsonProperty("updated_by")
    private String updatedBy;

    // 변경일
    @JsonProperty("updated_dt")
    private Timestamp updatedDt;
    
    @OneToMany(fetch = FetchType.LAZY, mappedBy = "boss")
    private List<Level> levelList;
    
    @OneToMany(fetch = FetchType.LAZY, mappedBy = "boss")
    private List<Pay> payList;
    
    
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
);

ALTER TABLE TB_A_BOSS COMMENT '보스 테이블';
```

> ![image](https://user-images.githubusercontent.com/17442343/120921713-de17e480-c6ff-11eb-9553-0cad6e900d3e.png)
