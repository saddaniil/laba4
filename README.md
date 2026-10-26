#include <stdio.h>

int laba2_1(int n, int d)
{
    if (d == n) return 0;
    if (n % d == 0) return d + laba2_1(n, d + 1);
    return laba2_1(n, d + 1);
}

void laba2_2(int n, int m)
{
    if (n > m) return;
    if (laba2_1(n, 1) > n) printf("%d ", n);
    laba2_2(n + 1, m);
}

int main()
{
    int N, M;
    printf("N M: ");
    scanf("%d %d", &N, &M);
    if (N < 1 || M <= N)
    {
        printf("Ошибка\n");
        return 1;
    }
    laba2_2(N, M);
    return 0;
}
