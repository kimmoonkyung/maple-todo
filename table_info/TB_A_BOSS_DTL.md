# Entity
```java
package com.mapletodo.test.model.entity;

import com.fasterxml.jackson.annotation.JsonProperty;
import lombok.AllArgsConstructor;
import lombok.Builder;
import lombok.Data;
import lombok.NoArgsConstructor;
import lombok.experimental.Accessors;

import javax.persistence.*;
import java.time.LocalDateTime;

// 관리자_기준정보 보스 상세
@Table(name = "TB_A_BOSS_DETAIL")
@Data
@Entity
@NoArgsConstructor
@AllArgsConstructor
@Builder
@Accessors(chain = true)
public class BossDetail {

    // id
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @JsonProperty("id")
    private Long id;

    // 주일구분
    @JsonProperty("day_div")
    private String dayDiv;

    // 난이도
    @JsonProperty("level_cd")
    private String levelCd;

    // 난이도명
    @JsonProperty("level_name")
    private String levelName;

    // 결정석가격
    @JsonProperty("pay")
    private Integer pay;

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

    @ManyToOne
    private Boss boss;

}
```

# DB
```sql
CREATE TABLE TB_A_BOSS_DTL
(
    `id`          BIGINT         NOT NULL    AUTO_INCREMENT COMMENT 'id', 
    `day_div`     VARCHAR(2)     NULL        COMMENT '주일구분', 
    `level_cd`    VARCHAR(2)     NULL        COMMENT '난이도', 
    `level_name`  VARCHAR(10)    NULL        COMMENT '난이도명', 
    `pay`         INT            NULL        COMMENT '결정석가격', 
    `created_by`  VARCHAR(30)    NULL        COMMENT '생성자', 
    `created_dt`  DATETIME       NULL        COMMENT '생성일', 
    `updated_by`  VARCHAR(30)    NULL        COMMENT '변경자', 
    `updated_dt`  DATETIME       NULL        COMMENT '변경일', 
    `boss_id`     BIGINT         NULL        COMMENT '보스ID', 
    CONSTRAINT  PRIMARY KEY (id)
)ENGINE = InnoDB DEFAULT CHARACTER SET = utf8mb4 COLLATE = utf8mb4_bin;

ALTER TABLE TB_A_BOSS_DETAIL COMMENT '보스 상세';

ALTER TABLE TB_A_BOSS_DETAIL
    ADD CONSTRAINT FK_TB_A_BOSS_DETAIL_boss_id_TB_A_BOSS_id FOREIGN KEY (boss_id)
        REFERENCES TB_A_BOSS (id) ON DELETE RESTRICT ON UPDATE RESTRICT;
```

> day_div로 매주 목 배치 수행
