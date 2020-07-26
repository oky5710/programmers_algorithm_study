# 전화 번호부

- phone_book을 정렬하면 인접한 값만 비교 가능

```
import java.util.Arrays;
class Solution {
    public boolean solution(String[] phone_book) {
        boolean answer = true;
        Arrays.sort(phone_book);
        for(var i=0; i<phone_book.length-1; i++){
            if(phone_book[i].indexOf(phone_book[i+1]) == 0 || phone_book[i+1].indexOf(phone_book[i]) == 0){
                answer = false;
                return false;
            }
        }
        return answer;
    }
}
```
