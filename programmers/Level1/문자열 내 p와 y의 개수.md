# 문자열 내 p와 y의 개수
문자열 내 알파벳을 p 혹은 y의 대/소문자를 파악해 각 알파벳의 수가 같은지 여부를 반환한다.

알파벳 별로 로직을 구하기에는 char을 쓰는 게 좋다.
여기선 equals()를 쓰기 위해 기본 자료형 char이 아닌 `참조 자료형 Character`를 사용했다.

또한 캐릭터를 지칭할 때는 큰 따옴표가 아닌 `작은 따옴표`를 사용해야 했다.

<br>

## 풀이
```
class Solution {
    boolean solution(String s) {
        int pCnt = 0;
        int yCnt = 0;

        for (int i = 0; i < s.length(); i++) {
            Character c = s.charAt(i);
            if (c.equals('p') || c.equals('P')) { pCnt++; }
            if (c.equals('y') || c.equals('Y')) { yCnt++; }
        }
        
        if (pCnt == yCnt) { return true; } 
        else { return false; }
    }
}
```
