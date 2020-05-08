function solution(citations) {
    let answer = 0;
    
    while (true) {
        const n = citations.length;
        const h = citations.filter(v => v >= answer).length;
        const under = citations.filter(v => v < answer).length;
        
        if (h + under === n && answer === h) {
            break;
        } 
        answer++;
    }
    
    return answer;
}