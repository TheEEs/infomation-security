# An Toàn bảo mật thông tin
## 1. Prime Numbers
## 2. Greatest common divisor
## 3. Ring n(modulo n ring)
> is a array of number from (1..n-1) with 2 operations:
> **Addition**: for every a,b; we have (a+b) = (a+b) mod n
> **Multiplication** : (a\*b) = (a\*b) mod n
> *0* are called harmonical element since a + 0 = 0 + a = a
> *1* is called unit element since a*1 = 1*a = a
>  A ^M - A \* A ^ (M-1) MOD N 

## 4. The inverse element
Given an **A** belongs to Zn, if there are a number **b** that **a**\***b** = 1. Then **b** is the inverse element of **a**. (written as **a**^-1)
> E.g : N = 23, a = 5, then b is 14 since 5.14 = 70 * 23 = 1

If GCD(N,a) = 1 then only exist one *b* number that sastifies : a * b = 1 mod n
We have **Phi** Euler function of a number N:
If n N = p1^(a1) . p2^(a2) . ... . pk(ak) then **Phi(N)** is defined as:
**Phi(N)** = (p1-1).p1^(a1-1) . (p2-1).p2^(a2-1) ..... (pk-1).pk^(ak-1)
or : **Phi(N)** - N\*(1-1/p1) * (1-1/p2) ... * (1-1/pk)

#### Euler Theorem:
> For each number n, we have: a^**Phi(N)** = 1 mod n if (a,n) = 1
> There are only **Phi(N)** a(s) that sastify (a,n) = 1


## 5. The Extended Euclidean
Used to find an inverse number of **a** in **Zn**.

Input : a,n; (a,n) = 1 . Output : a^-1 on **Zn**

Algorithm in peseu-do code:
```ruby
g0 =n
g1 = a
v0 = 0
v1 = 1
i = 1
while gi != 0
    y = g(i-1) % gi
    g(i+1) = g(i-1) - gi * y
    v(i+1) = v(i-1) - vi * y
    i += 1
end
if v(i-1) > 0 
    return v(i-1)
else return n+v(i+1)
```
 **E.G** : N = 43, a = 11, find a^-1 on **Z43**.
 
 Fast exponent algorithm: 
> How to compute a^m mod n quickly ?

Input: a,m and n
Output : a^m mod n

Solution: 

* Represent m in binary form m = b(k)b(k-1)..b(1)b(0) (*chiều từ thấp đến cao*)
* j = 0, ret = a;
* then excecute the following peseudo code:
```ruby
while k >= j
    if b(k) == 1
        ret = (ret * a) mod n;
    end
    a = (a*a) mod n;
    j += 1
end
```
 
 
 
