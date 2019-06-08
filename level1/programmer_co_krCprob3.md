<h5>동적할당으로 입력한 숫자만큼 "수박"반복출력하기</h5>

<pre>
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>
char* solution(int n) {
	// 리턴할 값은 메모리를 동적 할당해주세요.
	if (n <= 10000) {
		char* answer = (char*)malloc(sizeof(char) * 3 * n + 1);
		char c[3] = "수";
		char s[3] = "박";
		char ch[sizeof(c) * 10000 + 1] = "";
		for (int i = 1; i <= n; i++) {
			if (i % 2 != 0) {
				strcat(ch, c);
			}
			else {
				if (i % 2 == 0) {
					strcat(ch, s);
				}
			}
		}
		answer = ch;
		return answer;
	}
}

int main() {
	printf("인자값 3: %s\n", solution(3));
	printf("인자값 100: %s\n", solution(10000));
}

실행결과
<hr>
인자값 3: 수박수
인자값 100: 수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박수박
</pre>



