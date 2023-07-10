# Array2D

import java.util.*;
 
public class Main {
    public static void main(String[] args) throws Throwable {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int arr[] = new int[n];
        for(int i=0;i<n;++i){
            arr[i] = sc.nextInt();
        }
        int ans=ArrayProblem6(n,arr);
        System.out.println(ans);
    }
    public static int ArrayProblem6(int n, int[] arr){
        // Write code here
		//5
		//2 4 1 6 7
 
		//prev=-1,ans=max_value,i=0
		//prev=0,ans=max_value,i=0
		//i=1,ans=1,prev=1
		//i=2
		//i=3,ans=1,prev=3
		//
		int prev = -1;
		int ans = Integer.MAX_VALUE;
		for(int i=0;i<n;i++){
			if(arr[i]>0 && arr[i]%2==0){
				//approach 1
				if(prev == -1){
					prev = i;
				}
				else{
					ans=Math.min(ans,i-prev);
					prev=i;
				}
				// approach 2
				// if(prev!=-1){
				// 	ans=Math.min(ans,i-prev);
				// }
				// prev=i;
			}
		}
		if(ans == Integer.MAX_VALUE){
			return -1;a
		}
		return ans;
    }
}
