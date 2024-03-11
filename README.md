# Custom-Sort-String
You are given two strings order and s. All the characters of order are unique and were sorted in some custom order previously.  Permute the characters of s so that they match the order that order was sorted. More specifically, if a character x occurs before a character y in order, then x should occur before y in the permuted string.  

class Solution(object):
    def customSortString(self, order, s):
        char_count = {char: 0 for char in order}
        for char in s:
            if char in char_count:
                char_count[char] += 1
    
        sorted_s = ''
        for char in order:
            sorted_s += char * char_count[char]
    
        for char in s:
            if char not in order:
                sorted_s += char

        return sorted_s
