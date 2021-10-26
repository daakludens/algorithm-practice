# x만큼 간격이 있는 n개의 숫자
x의 배수를 n개 만큼 배열에 넣어 반환하면 된다.

여기서 중요한 건 넘겨지는 숫자가 int로 담을 수 없는 큰 값이 올 수도 있다는 점이다.
그래서 x를 int 그대로 사용하면 answer 배열에 담기는 값은 int가 되서 큰 값을 넣을 수 없다.
따라서 x를 long 자료형으로 변환을 해준 다음 answer 배열에 넣어줘야 제대로 동작한다.

<br>

## 풀이
```
class Solution {
    public long[] solution(int x, int n) {
        long[] answer = new long[n];
        long temp = x;
        
        for (int i = 0; i < n; i++) {
            answer[i] = temp * (i + 1);
        }
        
        return answer;
    }
}
```
