### 피보나치 수열 값을 1234567로 나머지값 구하기

<pre>
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

long long solution(int n) {
	long long answer = 0;
	long long second = 1;
	long long sum = 0;
	if (n > 0) {
		for (int i = 0; i < n; i++) {
			sum = answer + second;
			answer = second;
			second = sum;
		}
	}
	return answer % 1234567;
}

int main() {
	printf("인자값 3: %d\n", solution(3));
	printf("인자값 5: %d\n", solution(5));
	printf("인자값 100: %d\n", solution(100));
}

<hr>

인자값 3: 2
인자값 5: 5
인자값 100: 1047261
</pre>

