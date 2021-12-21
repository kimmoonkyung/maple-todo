# maple-todo -> maple-helper .. melper ?
```
    maple.gg에서 캐릭터정보 가져오는 것은 알려져 있는 메이플api를 통해 가져오는 것 같음.
    rest가 아닌 soap
    
    스프링부트+리액트로 화면 구성하고
    앱은 
```





































# maple-todo


> Spring Boot
>   
    JPA
    GRADLE
    Spring Batch
    LOMBOK
    VALIDATION
    AOP
  
  
> AWS

> React

> MySQL
>   > [TB_A_USER ❗](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_USER.md)
>   > 
>   > [TB_A_USER_HST❗](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_USER_HST.md) 
>   > entity listener
>   > 
>   > [TB_A_BOSS ✓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_BOSS.md)
>   > 
>   > [TB_A_BOSS_DTL ✓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_BOSS_DTL.md)
>   > 
>   > [TB_A_BOSS_HST ❓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_BOSS_HST.md)
>   > entity listener
>   >
>   > [TB_A_QUEST](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_QUEST.md)
>   > 
>   > [TB_A_INFO ❓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_INFO.md)
>   >
>   > [TB_A_INFO_HST ❓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_A_INFO_HST.md)
>   > entity listener
<!-- >   > [TB_A_ARCANE]() -->
>   > 
>   > [TB_U_TODO_BAS](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_U_TODO_BAS.md)
>   > 일 배치 초기화 하는 기본 템플릿으로 사용 할 것임
>   >
>   > [TB_U_TODO_DTL❓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_U_TODO_DTL.md)
>   > VIEW? 화면에 뿌릴용도로 사용 할 것임
>   > 
>   > [TB_U_TODO_HST❓](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_U_TODO_HST.md)
>   > TODO Y인거 적재 및 통계용 entity listener
>   >
>   > [TB_U_TODO_통계❓]()
>   > 
>   > [TB_U_CHARACTER](https://github.com/kimmoonkyung/maple-todo/blob/main/table_info/TB_U_CHARACTER.md)
>   > 
<!-- Trigger는 JPA를 사용하면 이용 못하나 ? 엔티티 리스너를 사용해야하는것인가 비슷하지만 다른 느낌인데 -->
<!-- 엔티티 리스너로 하는게 맞는 것 같음.  -->


## Project Structure
```
1. model
    Entity(ex User.class)
    1. listener
    2. history
        1. (ex Entity History)
    3. network
        1. request
        2. response
2. controller
3. repository
4. service
5. support
```
