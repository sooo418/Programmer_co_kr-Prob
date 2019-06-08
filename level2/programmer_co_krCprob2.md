### N개의 최소공배수



<pre>
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

// arr_len은 배열 arr의 길이입니다.
int solution(int arr[], size_t arr_len) {
	int answer = 0;
	int mul;
	int lcm;
	int tmp;
	if (1 <= arr_len && arr_len <= 15) {
		for (int i = 0; i < arr_len; i++) {
			if (arr[i] > 100)
				return 0;
		}
		mul = arr[0];
		bool b = true;
		while (b) {
			lcm = mul;
			for (int i = 1; i < arr_len; i++) {
				if (lcm % arr[i] == 0) {
					b = false;
				}
				else {
					b = true;
					break;
				}
			}
			mul += arr[0];
		}
		answer = mul - arr[0];
	}
	return answer;
}

int main() {
	int arr[] = { 1,2,3 };
	for (int i = 0; i < sizeof(arr) / sizeof(int); i++) {
		printf("%d ", arr[i]);
	}
	printf("의 최소공배수: %d\n",solution(arr, sizeof(arr)/sizeof(int)));
	int arr2[] = { 2,6,8,14 };
	for (int i = 0; i < sizeof(arr2) / sizeof(int); i++) {
		printf("%d ", arr2[i]);
	}
	printf("의 최소공배수: %d\n", solution(arr2, sizeof(arr2) / sizeof(int)));
}

실행결과
<hr>
1 2 3 의 최소공배수: 6
2 6 8 14 의 최소공배수: 168
</pre>


