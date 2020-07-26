# 프린터

```
function solution(priorities, location) {
    var answer = 0;
    var complete = [];
    var cnt = 0; // 몇번째 뽑는지
    while(priorities.length > 0){ // 대기열이 0이 될때까지 반복
        var first = priorities.shift(); // 첫번째 원소 뽑아
        var flag = true; // first보다 큰게 있는지
        for(var i=0; i<priorities.length; i++){ // 큐에 있는 원소를 반복하여 first보다 큰게 있는지 확인
            if(first < priorities[i]){
                flag = false; // first보다 큰게 있으면 false
                break;
            }
        }
        if(flag){ // first보다 큰게 없으면
            complete.push(first); // 완료 배열에 담는다
            if(cnt === location){
                priorities = []; // 대기열을 0으로 만들고
                answer = complete.length; // 완료 배열의 길이 값을 결과에 저장 
            }
        } else {
            priorities.push(first);
            if(cnt === location) { // 현재 뽑은 것보다 우선 순위가 높은게 있어서 뒤로 돌려야할 때 
                location = cnt + priorities.length;
            }
        }
        cnt++;
    }
    return answer;
}
```
