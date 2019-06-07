<h5>3n+1문제</h5>

<pre>
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
int solution(int num) {
	int answer = 0;
	if (1 <= num && num < 80000000) {
		while (answer < 450) {
			if (num % 2 == 0) {
				num /= 2;
				answer++;
				if (num == 1)
					return answer;
			}
			if (num % 2 != 0) {
				if (num == 1)
					return answer;
				num = num * 3 + 1;
				answer++;
			}
		}
		return -1;
	}
	printf("값을 확인하세요.");
	return 0;
}
int main() {
	printf("인자값 11: %d\n", solution(11));
	printf("인자값 626331: %d\n", solution(626331));
}
실행결과
<hr>
인자값 11: 14
인자값 626331: -1
</pre>



