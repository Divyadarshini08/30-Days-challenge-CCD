**Problem: String rotation of each other.**

'''java
class Solution {
    public static boolean areRotations(String s1, String s2) {
        if (s1.length() != s2.length()) {
            return false;
        }

        String temp = s1 + s1;
        return kmpSearch(temp, s2);
    }

    // KMP pattern matching
    private static boolean kmpSearch(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();
        
        int[] lps = computeLPS(pattern);
        
        int i = 0; // text index
        int j = 0; // pattern index
        
        while (i < n) {
            if (text.charAt(i) == pattern.charAt(j)) {
                i++;
                j++;
            }
            if (j == m) {
                // found pattern
                return true;
            } else if (i < n && text.charAt(i) != pattern.charAt(j)) {
                if (j != 0) {
                    j = lps[j - 1];
                } else {
                    i++;
                }
            }
        }
        
        return false;
    }

    // Build longest prefix suffix (LPS) array
    private static int[] computeLPS(String pattern) {
        int m = pattern.length();
        int[] lps = new int[m];
        int len = 0;
        int i = 1;
        
        while (i < m) {
            if (pattern.charAt(i) == pattern.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            } else {
                if (len != 0) {
                    len = lps[len - 1];
                } else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        return lps;
    }
}
