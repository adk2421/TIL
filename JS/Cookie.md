# 자바스크립트 쿠키

- 쿠키 값 저장하기
```
document.cookie = "key=value";
```

- 쿠키 값 가져오기

```
function getCookie(key) {
	if (document.cookie != null) {
    	var cookies = document.cookie.split(";");
        
        for (var i in cookies) {
        	if (cookies[i].indexOf(key) >= 0) {
            	return cookies[i].replace(key + "=","").trim();
			}
		}
	}
	return "";
}
```
>document.cookie를 출력했을 때 `cookie1=value1; cookie2=value2` 형식으로 나오기 때문에 따로 처리를 해주어야 한다.
