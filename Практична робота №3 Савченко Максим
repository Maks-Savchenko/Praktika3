#include <stdio.h>

long long count_numbers(int p) {
    if (p == 1) return 2; // Якщо розряд тільки один, є два числа: 5 і 9

    long long dp_5[p + 1], dp_9[p + 1], dp[p + 1];
    
    dp_5[1] = 1;
    dp_9[1] = 1;
    dp[1] = 2;
    
    for (int i = 2; i <= p; i++) {
        dp_5[i] = dp_9[i-1] + (i >= 3 ? dp_9[i-2] : 0);
        dp_9[i] = dp_5[i-1] + (i >= 3 ? dp_5[i-2] : 0);
        dp[i] = dp_5[i] + dp_9[i];
    }

    return dp[p];
}

int main() {
    int p;
    printf("Введіть кількість розрядів: ");
    scanf("%d", &p);

    long long result = count_numbers(p);
    printf("Кількість чисел з %d розрядів: %lld\n", p, result);
    return 0;
}
