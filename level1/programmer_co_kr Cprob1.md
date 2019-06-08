<h5>solution(int n)함수를 사용하여 n값의 약수를 모두 더한값 구하기</h5>

<pre>
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
int solution(int n) {
	int answer = 0;
​	if (0 <= n & n <= 3000) {
​		printf("%d의 약수는 ", n);
​		for (int i = 1; i <= n; i++) {
​			if (n%i == 0) {
​				if (i == n) {
​					printf("%d입니다. ", i);
​					answer += i;
​				}
​				else {
​					printf("%d,", i);
​					answer += i;
​				}
​			}
​		}
​		printf("이를 모두 더하면 %d입니다.\n", answer);
​	}
​	else {
​		printf("값을 확인해주세요. 0~3000");
​	}
​	return answer;
}
int main() {
	solution(3000);
return 0;
}
실행결과
<hr>
5의 약수는 1,5입니다. 이를 모두 더하면 6입니다.
3000의 약수는 1,2,3,4,5,6,8,10,12,15,20,24,25,30,40,50,60,75,100,120,125,150,
200,250,300,375,500,600,750,1000,1500,3000 입니다. 이를 모두 더하면 9360입니다.
</pre>



