# String Operations in C (Without Using Library Functions)

## Code

```c
#include <stdio.h>

int length_ams(char str_ams[]) {
    int i_ams = 0;
    while (str_ams[i_ams] != '\0')
        i_ams++;
    return i_ams;
}

void copy_ams(char dest_ams[], char src_ams[]) {
    int i_ams = 0;
    while (src_ams[i_ams] != '\0') {
        dest_ams[i_ams] = src_ams[i_ams];
        i_ams++;
    }
    dest_ams[i_ams] = '\0';
}

void reverse_ams(char str_ams[]) {
    int i_ams = 0, j_ams = length_ams(str_ams) - 1;
    char temp_ams;
    while (i_ams < j_ams) {
        temp_ams = str_ams[i_ams];
        str_ams[i_ams] = str_ams[j_ams];
        str_ams[j_ams] = temp_ams;
        i_ams++;
        j_ams--;
    }
}

void concat_ams(char str1_ams[], char str2_ams[]) {
    int i_ams = length_ams(str1_ams), j_ams = 0;
    while (str2_ams[j_ams] != '\0') {
        str1_ams[i_ams] = str2_ams[j_ams];
        i_ams++;
        j_ams++;
    }
    str1_ams[i_ams] = '\0';
}

int main() {
    char str1_ams[100], str2_ams[100], str3_ams[100];

    printf("Enter first string: ");
    scanf("%s", str1_ams);

    printf("Enter second string: ");
    scanf("%s", str2_ams);

    printf("\nLength of str1 = %d", length_ams(str1_ams));
    printf("\nLength of str2 = %d", length_ams(str2_ams));

    copy_ams(str3_ams, str1_ams);
    printf("\nCopy of str1 into str3 = %s", str3_ams);

    reverse_ams(str1_ams);
    printf("\nReverse of str1 = %s", str1_ams);

    concat_ams(str1_ams, str2_ams);
    printf("\nConcatenation of str1 and str2 = %s", str1_ams);

    return 0;
}
```

## Output

```
Enter first string: hello
Enter second string: world

Length of str1 = 5
Length of str2 = 5
Copy of str1 into str3 = hello
Reverse of str1 = olleh
Concatenation of str1 and str2 = ollehworld
```

## Algorithm

1. **Length Calculation**  
   - Start from index 0.  
   - Traverse characters until `\0`.  
   - Count characters and return length.  

2. **Copy**  
   - Initialize two arrays (source, destination).  
   - Copy each character until `\0`.  
   - Add `\0` at the end.  

3. **Reverse**  
   - Find length of string.  
   - Use two pointers: one at start, one at end.  
   - Swap characters while moving inward.  

4. **Concatenation**  
   - Move to the end of first string.  
   - Copy characters from second string to first.  
   - Add `\0` at the end.  

![img-alt](https://github.com/AyushSalvi1/VIT_DS/blob/main/images.jpeg?raw=true)
