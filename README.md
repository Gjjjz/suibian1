# suibian1
Student voting system
package suibian;

import java.util.Scanner;

public class xixi {

	static int[] arr = new int[3];
	static int[] brr = new int[5];
	static int x = 0, y = 0;

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);

		System.out.println("请输入每次博弈的总数：");
		for (int j = 0; j < 5; j++) {
			int b = sc.nextInt();
			brr[j] = b;
			System.out.println(brr[j]);
		}
		for (int i = 0; i < 5; i++) {
			f(brr[i], x, y);
			if (x % 2 == 0 && y % 2 != 0) {
				System.out.println("+");
			} else if (x % 2 == 0 && y % 2 == 0) {
				System.out.println("0");
			} else {
				System.out.println("-");
			}
		}
	}

	public static void f(int n, int me, int you) {
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入您规定的拿取数量：");
		for (int i = 0; i < 3; i++) {
			int a = sc.nextInt();
			arr[i] = a;
			System.out.println(arr[i]);
		}
		while (n > 0) {
			for (int i = 0; i < 3; i++) {
				n = n - arr[i];
				me = me + arr[i];
				f(n, y, x);
			}
		}
	}

}

