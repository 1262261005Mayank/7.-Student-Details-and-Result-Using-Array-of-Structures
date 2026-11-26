# 7.-Student-Details-and-Result-Using-Array-of-Structures
#include <stdio.h>

struct Student {
    int rollNo;
    char name[50];
    float marks[3];
    float total;
    float percentage;
};

int main() {
    int n, i;
    struct Student s[100];

    printf("Enter the number of students: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("\nEnter the roll number, name and marks of 3 subjects:\n");
        scanf("%d %s %f %f %f",
              &s[i].rollNo,
              s[i].name,
              &s[i].marks[0],
              &s[i].marks[1],
              &s[i].marks[2]);

        s[i].total = s[i].marks[0] + s[i].marks[1] + s[i].marks[2];
        s[i].percentage = s[i].total / 3.0f;
    }

    printf("\nRoll No | Name | Subject: 1 | Subject: 2 | Subject: 3 | Total | Percentage\n");
    for (i = 0; i < n; i++) {
        printf("%d | %s | %.0f | %.0f | %.0f | %.0f | %.2f\n",
               s[i].rollNo,
               s[i].name,
               s[i].marks[0],
               s[i].marks[1],
               s[i].marks[2],
               s[i].total,
               s[i].percentage);
    }

    return 0;
}
