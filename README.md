# janani
TOTAL_CHARS = 256
def distinct_character(str, n): 
    count = [0] * TOTAL_CHARS
    for i in range(n): 
        count[ord(str[i])] += 1
    distnct_max = 0
    for i in range(TOTAL_CHARS): 
        if (count[i] != 0): 
              distnct_max += 1    
    return  distnct_max
def smallestdistinct_substring(str):
    n = len(str)    
    distnct_max = distinct_character(str, n)
    minimum=n
    for i in range(n):   
        for j in range(n): 
            substring = str[i:j] 
            substring_length = len(substring) 
            substring_distinct_char = distinct_character(substring,substring_length)
            if (substring_length < minimum and distnct_max == substring_distinct_char):
                minimum = substring_length 
    return minimum
  
str = "abcda"
result = smallestdistinct_substring(str); 
print(result) 
