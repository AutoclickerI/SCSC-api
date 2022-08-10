## 멤버 등급 설정
기본적으로 관리자만 접근 가능한 메뉴
### 요청
#### URL
 `ADMIN /member`
#### data 파라미터
 **Not Required:**
<br>
<br>
#### 응답

**Success ResponseCode:** `200`

  **Content:**
   `{{id:1, username:"hello", name:"홍길동", admissionYear:"2022", major:"수리과학부", memberType:2}, {id:2, username:"world", name:"홍길순", admissionYear:"2022", major:"컴퓨터공학부", memberType:1}}`

<br>

**Error Response**

  **Code:** `401(UnAuthorized)`

  **Content:**`{error:'권한이 없는 사용자입니다.}`


## 멤버 등급 변경하기
### 요청
#### URL
`UPDATE /member/{id}/{memberType}`
#### URL 파라미터
 `Required:id[integer],memberType[integer]`

 **Success Response**
    **Code**: `204(No content)`
    <br>
    
  **Error response**
  **code**: `401(Unauthorized)`
  **Content:**`{error:'권한이 없는 사용자입니다.}`
  <br>

  **code**: `404(Not found)`
  **content:**`{error:'not found}`



