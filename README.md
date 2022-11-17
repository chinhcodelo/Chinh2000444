#include<stdio.h>
#include<math.h>
int getDigit(long long n); // lay chu so dau tien cua n
int totalDigit(long long n); // tinh tong cac chu so cua n
int maxDigit(long long n); // tim max cua cac chu so n
int countDigit(long long n); // dem cac chu so cua n
int check(int n); // kiem tra n co phai la chu so khac nhau 1 doi
int count(int a[], int n); // dem so lan xuat hien
void pushArray(int a[], int &n, int x); // day cac phan tu vao mang 1 chieu

void cau1();


void cauA(int h);
void cauB(int h);
void cauC(int h);
void cau2();
float cau3(int n);
float cau4(int n);
float cau5(int n);
float cau6(int n);
float cau7(int n);
float cau8(int n);
int cau9(int x, int n);
unsigned long long cau10(int x, int n);
float cau11(int x, int n);
int main() {
//	cau1();
//	printf("%lld", cau10(2, 5));
	cau2();
	return 0;
}


int getDigit(long long n) {
	int result;
	while(n != 0) { // trong khi n khac 0
		result = n % 10; // lay chu cuoi cung cua n
		n /= 10; // bot di 1 so cua n
	}
	return result;
}

int totalDigit(long long n) {
	int sum = 0;
	while(n != 0) {
		sum += n % 10; 
		n /= 10; // n = n / 10;
	}
	return sum;
}

int maxDigit(long long n) {
	int max = n % 10;
	while(n != 0) {
		if(max < n % 10) max = n % 10;
		n /= 10;
	}
	return max;
}

void pushArray(int a[], int &n, int x) {
	int i = 0;
	while(x != 0) {
		a[i] = x % 10;
		i++;
		x /= 10;
	}
}

int count(int n, int x) {
	int count = 0;
	int m = countDigit(n);
	int a[m];
	pushArray(a, m, n );
	for(int i = 0; i < m; i++) {
		if(x == a[i]) {
			count++;
		}
	}
	return count;
}

int check(int n) {
	int m = countDigit(n);
	int a[m];
	pushArray(a, m, n );
	for(int i = 0; i < m - 1; i++) {
		for(int j = i + 1; j < m; j++) {
			if(a[j] == a[i]) {
				return a[i];
			}
		}
	}
	return 0;
}

int countDigit(long long n) {
	int count = 0;
	while(n != 0) {
		n /= 10;
		count++;
	}
	
	return count;
}
void cau1() {
	unsigned long long n;
	printf("Nhap vao n = "); scanf("%lld", &n);
	printf("Chu dau tien cua n la: %d", getDigit(n));
	printf("\nTong cac chu so cua n la: %d", totalDigit(n));
	printf("\nSo luong chu trong n la: %d", countDigit(n));
	printf("\nMax = %d", maxDigit(n));
	check(n) ? printf("\n%d la so doi mot vi co %d so %d giong nhau", n, count(n, check(n)), check(n)) : printf("\n%d khong phai la so doi mot", n);
}


float cau3(int n) {
	float sum_1 = 0, sum_2 = 0;
	for(int i = 1; i <= n; i++) {
		if(i % 2 == 0) {
			sum_1 += i;
		} else {
			sum_2 += i;
		}
	}
	return sum_2 - sum_1;
}

float cau4(int n) {
	float sum = 0;
	for(int i = 1; i <= n; i++) {
		sum += 1.0 / i;
	}
	return sum;
}

float cau5(int n) {
	float sum = 0;
	for(int i = 0; i <= n; i++) {
		sum += 1.0 / (2 * i + 1);
	}
	return sum;
}


float cau7(int n) {
	float sum = 0;
	for(int i = 1; i <= n; i++) {
		sum += 1.0 / i + 1;
	}
	return sum;	
}

float cau6(int n) {
	float sum = 0;
	for(int i = 1; i <= n; i++) {
		sum += 1.0 / i * (i + 1);
	}
	return sum;
}

float cau8(int n) {
	float sum = 0;
	for(int i = 0; i <= n; i++) {
		sum += (i * 2 + 1) / (i * 2 + 2); 
	}
	return sum;
}
int cau9(int x, int n) {
	return pow(x, n);
}
unsigned long long cau10(int x, int n) {
	unsigned long long sum = 0;
	for(int i = 1; i <= n; i++) {
		sum += pow(x, i);
	}
	return sum;	
}

float cau11(int x, int n) {
	int sum_1 = 0;
	int sum_2 = 1;
	for(int i = 1; i <= n; i++) {
		if(i % 2 == 0) {
			sum_1 += pow(x, i);
		} else {
			sum_2 += pow(x, i);
		}
	}
	return sum_2 - sum_1;
}

void cau2() {
	int h;
	printf("Nhap vao h = ");
	scanf("%d", &h);
	printf("\t\t\tCau A\n");
	cauA(h);
	printf("\t\t\tCau B\n");
	cauB(h);
	printf("\t\t\tCau C\n");
	cauC(h);
}

void cauA(int n) {
	for(int i = 1; i <= n; i++) {
		for(int j = 1; j <= i; j++) {
			printf("*");
		}
		printf("\n");
	}
}
void cauB(int n) {
	for(int i = n; i >= 1; i--) {
		for(int j = 1; j <= i; j++) {
			printf("*");
		}
		printf("\n");
	}	
}
void cauC(int n) {
	for(int i = 1; i <= n; i++) {
		for(int j = 1; j <= n - i; j++) {
			printf(" ");
		}
		
		
		for(int j = 1; j <= 2 * i - 1; j++) {
			printf("* ");
		}
		printf("\n");
	}
}
