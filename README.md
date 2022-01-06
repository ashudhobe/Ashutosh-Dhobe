package sau;

import java.util.Scanner;

public class Q {
	public static void main(String[] args) {
		String str = "";
		int j = 0;
		Scanner sc = new Scanner(System.in);
		int n = Integer.parseInt(sc.next());
		while(n >= 1) {
			String s1 = sc.next();
			String s2 = sc.next();
			if(s2.indexOf(s1) != -1) {
				str += "YES\n";
			} else {
				for(int i=0; i<s1.length(); i++) {
					if(s2.indexOf(s1.charAt(i)) != -1) {
						j++;
						s2 = s2.substring(0, s2.indexOf(s1.charAt(i))) + '_'
			              + s2.substring(s2.indexOf(s1.charAt(i)) + 1);
					}
				}
				if(j == s1.length()) {
					str += "YES\n";
				} else {
					str += "NO\n";
				}
			}
			j = 0;
			n--;
		}
		System.out.println(str);
	}
}
