# GFM의 표준 Markdown에 대한 확장 부분의 사용법

## < Table; 표 >
- 각 행은 `|`으로 구분되어진다.
- `---`을 사용하여 행의 내용에 구분을 준다.
- `:---`, `:---:`, `---:` 을 사용하여 각 열의 정렬 상태를 정의한다.
- `-`의 갯수를 정할 땐, txt파일로 보았을 때도 가독성이 좋을 수 있도록 표현하는 것이 좋다.
- `:------:` 로 열의 수를 구분하게 되면 본문에 아무것도 넣지 않아도 공백인 빈칸으로 출력이 가능하다.
- 정해놓은 열 밖으로 넘어간 열은 무시한다.

>ex) 입력  
>`| 머리말 1 | 머리말 2 | 머리말 3 | 머리말 4 |`  
>`| :------: | :------: | :------: | :------: |`  
>`| 본문 1 | 본문 2 | 빈칸 -> | |`  
>`| 본문 1 | 본문 2 | 본문 3 | 본문 4 | 무시 내용 |`  

>ex) 출력  
>| **머리말 1** | **머리말 2** | **머리말 3** | **머리말 4** |  
>| :------: | :------: | :------: | :------: |  
>| 본문 1 | 본문 2 | 빈칸 -> | |  
>| 본문 1 | 본문 2 | 본문 3 | 본문 4 | 무시 내용 |  

## < Task list item ; Todo 리스트 만들기 >
- `- []`, `- [x]` 를 사용하여 Todo list를 구현 가능하다.
- `- []` ; 입력 시 확인 표시 취소
- `- [x]` ; x(소문자) 와 X(대문자) 모두 사용 가능하며, 입력 시 확인 표시
- 들여 쓰기 가능하다.

>ex) 입력   
>`- [ ] 학생회 기획안 작성하기`  
>`- [ ] 후배분들과 밥약속 잡기`  
>` - [ ] 시간 언제 만나지?`  
>`- [x] 스터디 공부하기`  

>ex) 출력  
>- [ ] 학생회 기획안 작성하기  
>- [ ] 후배분들과 밥약속 잡기  
> - [ ] 시간 언제 만나지?
>- [x] 스터디 공부하기  

## < StrikeThrough; 취소선>
- 취소선을 넣고 싶은 부분 앞뒤에 `~~` 입력
- `~~` 를 부분의 앞에만 입력하고 뒤에 입력하지 않아 끝맺음을 안하고 줄을 넘어가게 된다면 취소선이 생기지 않는다.

>ex) 입력  
>`~~ 를 이용하여 취소선을 ~~생기게~~ 할겁니다.`  
>`이렇게 ~~ 을 사용할 때 끝맺음을 안하고 중간에`  
>`줄을 넘어가게 된다면 취소선이 생기지 않습니다.~~`  

>ex) 출력  
>~~ 를 이용하여 취소선을 ~~생기게~~ 할겁니다.  
>이렇게 ~~ 을 사용할 때 끝맺음을 안하고 중간에  
>줄을 넘어가게 된다면 취소선이 생기지 않습니다.~~

## < Autolink; 자동링크 >
- http를 적지 않아도 URL을 인식하여 하이퍼링크로 만들어 준다.
  - 링크 중 `<`이 들어가면 `<` 전까지를 링크로 인식한다.
  - 링크 마지막이 `)`로 끝난다면 링크의 `( )`에 맞춰서 인식한다. 링크가 )로 끝나지 않으면 상관없다.
  - 링크 마지막 부분이 `? , ! , . , , , : , * , _ , ~`로 끝나는 경우 -> 링크로 인식하지 않음

>ex)   
>`www.naver.com`  
>`www.naver.com</notberecognized`  
>`www.naver.com/(recognized)`  
>`www.naver.com!`  

>ex) 출력
>www.naver.com  
>www.naver.com</notberecognized  
>www.naver.com/(recognized)
>www.naver.com!

## < Disallowed Raw HTML; 허용되지 않는 원시 HTML >
- `tagfilter` HTML 출력을 렌더링 할 때 밑의 HTML 태그들이 필터링되는 확장을 활성화 한다.
  - `<title>`
  - `<textarea>`
  - `<style>`
  - `<xmp>`
  - `<iframe>`
  - `<noembed>`
  - `<noframes>`
  - `<script>`
  - `<plaintext>`
