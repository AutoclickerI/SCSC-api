**게시글**
----
  게시글 id를 이용하여 접속   
  유저 id로부터 게시글 접속 권한을 확인 후 게시글의 내용과 작성자, 조회수, 댓글 목록을 반환   
  덧글 여부는 indent로 구분

* **URL**

  `Local Host(임시)`   
  `/users/:post/post_id`

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
   
   `post_id=[integer]`

* **Data Params**

  `user_id=[string]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    `{ post_id : 412, post_name : "Lorem ipsum", post_hit : 12, post_main : "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
    post_reply : [[ reply_id : 0, indent : 0, reply_main : "0번 댓글입니다" ], [reply_id : 1, indent : 1, reply_main : "0번 댓글의 덧글입니다"], [reply_id : 2, indent : 0, reply_main : "1번 댓글입니다"]]}`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Page doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/:1post/412",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
