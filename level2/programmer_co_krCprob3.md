### 스킬트리

<pre>
    #define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>

// skill_trees_len은 skill_trees의 길이입니다.
int solution(char* skill, char* skill_trees[], size_t skill_trees_len) {
	int answer = 0;
	char token[2];
	token[0] = skill[0];
	token[1] = '\0';
	char stemp[10];
	char stemp2[10];
	int skill_len = strlen(skill);
	bool b;
	bool b2;
    bool skill_b;
    if(2 <= skill_len && skill_len <= 26){
        if(2 <= skill_trees_len && skill_trees_len <= 20){
            for(int q = 0; q < skill_len; q++){
                for(int w = q + 1; w < skill_len; w++){
                    if(q!=w){
                        skill_b = true;
                    }
                    else
                        skill_b = false;
                }
            }
        }
    }
    if(skill_b==true){
	    for (int i = 0; i < skill_trees_len; i++) {
		    stemp[0] = '\0';
		    strcpy(stemp, skill_trees[i]);
		    for (int j = 1; j < skill_len; j++) {
			    b = false;
			    strtok(stemp, token);

			    if (stemp[0] == skill[0]) {
				    b = true;
				    break;
			    }
			    else if (strchr(stemp, skill[j])) {
				    b = false;
				    break;
			    }
			    else if(!(strchr(stemp, skill[j]))) {
				    b = true;
			    }
		    }
		    if (b == true) {
			    for (int j = 1; j < skill_len; j++) {
				    b2 = false;
				    stemp[0] = '\0';
				    strcpy(stemp, skill_trees[i]);
				    stemp2[0] = '\0';
				    if (strchr(stemp, skill[j])) {
					    strcpy(stemp2, strchr(stemp, skill[j]));
				    }
                    else if (!strchr(stemp, skill[j])&&skill[j]==skill[skill_len - 1]) {
					    b2 = true;
					    break;
				    }
				    else if (!strchr(stemp, skill[j]) && strchr(stemp,skill[j+1])) {
    					break;
	    			}
				    else
					    break;

				    for (int t = 0; t < j; t++) {
					    if (strchr(stemp2, skill[t])) {
						    b2 = false;
						    break;
					    }
					    else if(!strchr(stemp2,skill[t])) {
						    b2 = true;
					    }
                    
	    			}
    			}
	    	}
	    	if (b == true && b2 == true) {
	    		answer++;
            }
        }
    }
	return answer;
}

int main(){
char *skill = "CBD";
char *skill_trees[] = { "BACDE", "CBADF", "AECB", "BDA" }
printf("성공한 트리: %d\n", solution(skill, skill_trees, strlen(skill_trees)));

char *skill2 = "CBED";
char *skill2_trees[] = { "ACFED", "ACFGD", "ACBD", "ACFBED" }
printf("성공한 트리2: %d\n", solution(skill2, skill2_trees, strlen(skill2_trees)));
}

char *skill3 = "DBC";
char *skill3_trees[] = { "DAEBC", "ADEC", "BCE", "ADBEC", "EBC" }
printf("성공한 트리3: %d\n", solution(skill3, skill3_trees, strlen(skill3_trees)));
실행결과
<hr>
성공한 트리: 2
성공한 트리2: 1
성공한 트리3: 2
</pre>

