**게시판**
----
  게시판 id를 이용하여 접속   
  게시판의 글과 작성자, 조회수 목록을 반환   
  게시판 최상단에 위치할 게시글의 id를 변수로 받아와서 페이지 재구성 가능   

* **URL**

  `Local Host(임시)`   
  `/users/:board_id?top=post_id`

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   `board_id=[integer]`   
   `post_id=[integer]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
