<h5>XY그리드</h5>

<pre>
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main(void) {
	int a;
	int b;
	scanf("%d %d", &a, &b);
	for (int i = 0; i < b; i++) {
		for (int j = 0; j < a; j++) {
			printf("*");
		}
		printf("\n");
	}
	return 0;
}
실행결과
<hr>
5 3
*****
*****
*****
</pre>

