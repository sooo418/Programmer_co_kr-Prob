<h5>두 값 사이의 값들 더한값 구하기</h5>

<pre>
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
long long solution(int a, int b) {
	long long answer = 0;
	if (-10000000 <= a & a <= 10000000 & -10000000 <= b & b <= 10000000) {
		if (a == b) {
			return a;
		}
		if (a < b) {
			for (int i = a; i <= b; i++) {
				answer += i;
			}
		}
		if (a > b) {
			for (int i = a; i >= b; i--) {
				answer += i;
			}
		}
		return answer;
	}
	else {
		printf("값을 확인하세요.\n");
		return answer;
	}
}
int main() {
	printf("입력값:%d, %d 출력값:%d\n", 3, 5, solution(3, 5));
	printf("입력값:%d, %d 출력값:%d\n", 3, 3, solution(3, 3));
	printf("입력값:%d, %d 출력값:%d\n", 5, 3, solution(5, 3));
	printf("입력값:%d, %d 출력값:%d\n", 10000001, -10000001, solution(10000001, -10000001));
}

실행결과
<hr>
입력값:3, 5 출력값:12
입력값:3, 3 출력값:3
입력값:5, 3 출력값:12
값을 확인하세요.
입력값:10000001, -10000001 출력값:0
</pre>

