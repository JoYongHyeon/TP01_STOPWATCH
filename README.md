# 스탑워치 - 기능설명
```
화면에 표시된 타이머(00:00)
각각 Start, Stop, Reset 3개의 버튼
Start 버튼을 누를 경우 타이머가 시작이 되며,
Stop 버튼을 누를 경우 타이머의 시간은 멈추게 된다.
Reset 버튼을 누를 경우 Start 버튼 또는 Stop 버튼의 작동과 상관없이 타이머의 시간은 00:00로 초기화되며 타이어는 멈춘다.
```
----------------------------
# 함수호출 vs 함수참조
### 이론적으로 당연하게 알고 있고 그렇게 안 할 거라고 생각했던 부분인데 부끄럽다..
### 다음 내가 실수한 소스를 올려본다.
```c
clearInterval(interval);
interval = setInterval(startTimer, 10);  

function startTimer()
{
    ms++;
        
        if(ms <= 9)
        {
            tens.innerText = "0" + ms;
        }
        if(ms > 9)
        {
            tens.innerText = ms;
        }
        if(ms > 99)
        {
            second++;
            seconds.innerText = "0" + second;

            ms = 0;
            tens.innerText = "0" + ms;
            
            if(second > 9)
            {
                seconds.innerText = second;
            }
        }
}
```
### 함수 호출
* 함수 식별자 뒤에 괄호를 쓰면 함수 본문(Body)을 실행한다.
* 함수를 호출한 표현식은 반환값이 된다. ``` setInterval(startTimer(), 10); ```

### 함수 참조 
* 함수 식별자 뒤에 괄호를 쓰지 않으면 함수는 실행되지 않는다.
* ``` setInterval(startTimer, 10); ```
