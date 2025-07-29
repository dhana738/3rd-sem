# 3rd-sem
1.decimal to binary
n=int(input())
binaryresult=""
if(n==0):
    print(0)
    else
    while(n!=0):
        rem=n%2
        binaryresult+=str(rem)
        n=n//2
    print(binaryresult[::-1])
2.binary to decimal code
s=(input())#1111
p2=1
result=0
for i in s[::-1]:
    if(i=="1"):
        result=result+p2
    p2=p2*2
print(result)
dry run
p2=1
result=0
p2=2
p2=4
result=5
p2=8
result=13

#1              1              0            1
 1 *2 power 3   1 *2 power 2   0 *2power 1  1 *2 power 0
3.bit operaters
and: all t=t
     one f=f
or:all f=f
   one t=t
xor:no of 1 even=0
    no of 1 odd=1
right shift: >>
            formula: x//2 power k
left shift:<<
           formula: x*(2**(k)) x multipy by 2 and power of k)
here we may have 32 bit or 64 bit soo here left means we have 0s left side thus more number
4.check set bit
bit is called set-bit if it is 1 
use left shift(1<<k) for the another binary number to perform in and operation
use and operator,if answer is all 0s then it is not a set bit!!
                 if answer include 1 then it is a set bit!! 
n=int(input())
k=int(input())
    if((n&(1<<k))==0):
        return False
    return True
5. change non set bit place to set bit
#will keep 1 in non set bit and rest all 0s
n=int(input())
k=int(input())
n=n|(1<<k) #or operation
return n
6. clear ith bit(change set-bit to non-set bit)
#1st left shift(1<<k) then negation then and operation with n
n=int(input())
k=int(input())
n=n&(~(1<<k))
print(n)
7. toggle ith bit
n=int(input())
k=int(input())
n=n^(1<<k)
print(n)
8.right most set-bit change to 0
functionality:
here for example: 16:10000 15:01111 soo from 1st appeared 1 in 16 we toggle in 15!
now n =16 and n-1=15 soo perform and operation on n,n-1
n=int(input())
n=n&(n-1)
print(n)
9. check whether it is power of 2
functionality:we have only 1 in all powers of 2!!!

10. generate subsets of a array
 total subsets: 1<<length of the array    
 functionality:   1: take :dont take    {1 2 3}
    2  1  0---- index
    0  0  0 {}
    0  0  1 {0th index number = 1}
    0  1  0 {1th index num = 2}
    0  1  1 { 0th ,1st index = 1 2 } 
    1  0  0 { 2nd index = 3}
    1  0  1 { 0th, 2nd index = 1 3 }
    1  1  0 { 1st,2nd index = 2 3}
    1  1  1 {0th 1st 2nd index = 1 2 3 }

sooo here 1<<0 ,1<<1 ,1<<2,------ till 1<<9
then number:0000 and 1<<0----- 1<<9
           ex: 0&(1<<0)
               0000
               0000    [1<<0]
              =0 soo it is false
          ex: 5&(1<<0)            initially i=0
              101
              001
            = 001 so '1' in 0th position we have a 1 thus true!
                                  i=1 increment as above is true!
             5&(1<<1)
              101
              010
            = 000 here 0s so false
                                  i=2 increment as above is true!
             5&(1<<2)
              101
              100
            = 100 so '1' in 2rd position we have a 1 thus true!

def generate(arr):
    n=len(arr)
    totalsubsets=(1<<n)
    ans=[]
    for val in range(totalsubsets): #initial val=0
        temp=[]
        for i in range(n): #initial i=0,1,2 n=3
            if(val&(1<<i)):
                temp.append(arr[i])
        ans.append(temp)
    return ans
arr=[1,2,3]
ans=generate(arr)
print(ans)






