# my_Codesimport java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] arr = new int[n];
            int[] b_arr = new int[n];
            for (int i = 0; i < n; i++) {
                arr[i] = sc.nextInt();
            }
            for (int i = 0; i < n; i++) {
                b_arr[i] = sc.nextInt();
            }
            int a = whoswho(arr);
            int b = whoswho(b_arr);
         System.out.println(a == b ? "Draw" : (a > b ? "Om" : "Addy"));
        }
    }

  static int whoswho(int[] arr) {
        int maxStreak = 0;
        int currentStreak = 0;
        for (int i = 0; i < arr.length; i++) {
        if (arr[i] > 0) {
             currentStreak++;
        } else {
           if (currentStreak > maxStreak) {
                maxStreak = currentStreak;
           }
          currentStreak = 0;
        }
     }
// Check one more time in case the longest streak ends at the end of the array
        if (currentStreak > maxStreak) {
            maxStreak = currentStreak;
        }
       return maxStreak;
    }
}
