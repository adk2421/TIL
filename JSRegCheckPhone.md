# 자바스크립트 휴대폰 번호 유효성 검사

- 숫자만 입력 가능 (정규식)
```
function inputNumberOnly(param) {
        const regex = /[^0-9]/ig;
        
        if (regex.test(param.value) === true)
        	param.value = param.value.replace(regex, "");
}
```
> 적용할 `input` 태그에 `oninput="inputNumberOnly(this)"`를 넣으면 적용 가능하다.

<br>

- 휴대폰 번호 유효성 검사 (정규식)
```
function regPhoneNum {
        const regPhone = /^01([0|1|6|7|8|9])([0-9]{3,4})([0-9]{4})$/;
        var phoneNum = document.getElementById("phoneNum").value;
        
        if (regPhone.test(phoneNum) === false) {
            alert("유효하지 않은 휴대폰번호 입니다.");
            return false;
        }
```
> 휴대폰 번호 형식에 맞게 유효성 검사

<br>

- 전화번호 형식(-)으로 변환
```
function phoneNumFormat(phoneNum) {
        var phone = "";
        
        if (phoneNum.length == 11)
            phone = phoneNum.substr(0, 3) + "-" + phoneNum.substr(3, 4) + "-" + phoneNum.substr(7, 4);
        else {
            phone = phoneNum.substr(0, 3) + "-" + phoneNum.substr(3, 3) + "-" + phoneNum.substr(6, 4);
        }
        
        return phone;
    }
```
> 전화번호를 숫자로만 받을 때 사용한다.
