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
    **Content:** 
    `{    [post_id : 412, post_name : "Lorem ipsum", post_hit : 12],     
       [post_id : 411, post_name : "dolor sit amet", post_hit : 11],     
       [post_id : 410, post_name : "consectetur adipiscing elit", post_hit : 13],     
       [post_id : 409, post_name : "sed do eiusmod", post_hit : 19],     
       [post_id : 408, post_name : "tempor incididunt", post_hit : 8] ....    }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Page doesn't exist" }`

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
