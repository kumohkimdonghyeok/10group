def search_horspool(T, P):
    m = len(P) 
    n = len(T) 
    t = shift_table(P)  
    i = m - 1  

    while i <= n - 1:
        k = 0
        while k <= m - 1 and P[m - 1 - k] == T[i - k]:
            k += 1
        if k == m:
            return i - m + 1  
        else:
            tc = T[i]  
            i += t[ord(tc)]  
    return -1

def shift_table(pat):
    m = len(pat)
    tbl = [m]*128
    for i in range(m-1):
        tbl[ord(pat[i])] = m-1-i
    return tbl
