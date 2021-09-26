# K번째수
이번 같은 경우는 2차원 배열에 대한 이해가 있다면 쉽게 풀 수 있다.

<br>

## 새롭게 시도한 부분
혹시 방법이 있을까 싶어 Arrays의 도큐먼트를 읽어 보다가 copyOfRange() 메서드를 발견했다. 
해당 메서드는 아규먼트로 기존 배열, 시작 인덱스, 끝 인덱스를 넣어서 지정된 길이의 배열을 복사해 리턴한다.
필요 배열만 선택할 수 있으니 이번 문제에 굉장히 적합한 메서드라 생각해 사용하게 됐다.

또한 주의할 점으로 commands에서 제공되는 인덱스는 자바의 인덱스를 고려하지 않은 숫자이다.
즉, 0부터 시작하지 않고 1부터 시작하기 때문에 시작 인덱스의 값을 하나 빼줘야 제대로 동작한다.
풀이는 아래와 같이 했다.

<br>

## 풀이
```
import java.util.*;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];        
        
        for (int i = 0; i < commands.length; i++) {
            int[] temp = Arrays.copyOfRange(array, commands[i][0]-1, commands[i][1]);
            Arrays.sort(temp);
            answer[i] = temp[commands[i][2]-1];
        }
        
        return answer;
    }
}
```

<br>

## 다음부터 고려할 점
그런데 내가 답을 제출할 때 저번에 6점이 오른 것과 달리 3점 밖에 안 올랐다.
내가 뭔가 잘못했나 싶었는데 다른 분들의 후기를 보니 라이브러리를 사용하면 그만큼 점수가 차감된다고 한다.
아마도 내가 찾아낸 copyOfRange()가 마음에 안 들었나 보다.
그래서 점수도 올리고 알고리즘을 공부할 겸 본인이 다 짜는 게 낫다고 한다.
고수님들께서 그러라시니... 그래야지...
