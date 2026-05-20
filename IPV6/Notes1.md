# Decimal    Binary    Hexadecimal
  0          0000      0
  1          0001      1
  2          0010      2
  3          0011      3
  4          0100      4
  5          0101      5
  6          0110      6
  7          0111      7
  8          1000      8
  9          1001      9
  10         1010      A
  11         1011      B
  12         1100      C
  13         1101      D
  14         1110      E
  15         1111      F


# Cheatsheet

# Decimal,Hex,  Binary (8-4-2-1)
0,        0,     0000
1,        1,     0001
2,        2,     0010
4,        4,     0100
8,        8,     1000


# IPV6

An IPV6 address is 128 bits.
There are 340 decilion IPV6 addresses are there.
There are 4 million IPV4 addresses are there.

Example IPV6

2001 : 0DB8 : 5917 : EABD : 6562 : 17EA : C92D : 59BD

So an IPV6 address is written in 32 hexadecimal character, Divided into 8 groups of 4 using colons.

2001 : 0DB8 : 5917 : EABD : 6562 : 17EA : C92D : 59BD / 64 means first half of the section would be the network portion and the second half would be the host portion.

Each part is called quartets.

2001 : 0000 : 0000 : 0000 : 20A1 : 0000 : 0000 : 34BD

if there are three 0000 quartets we use (::)

2001 :: 20A1 : 0 : 0 : 34BD

1. 2000 : AB78 : 0020 : 01BF : ED89 : 0000 : 0000 : 0001
Ans : 2000 : AB78 : 20 : 1BF : ED89 :: 1

2. FE80 : 0000 : 0000 : 0000 : 0002 : 0000 : 0000 : FBE8
Ans : FE80 :: 2 : 0 : 0 : FBE8

All quartets have 4 hexadecimal character thats why its called quartets.

1. FE80 :: 1010 : 2FC : 0 : 9
Ans : FE80 : 0000 : 0000 : 0000 : 1010 : 02FC : 0000 : 0009

2. 2001 : DB8 : 1 : B23 : 2309 :: C1
Ans : 2001 : 0DB8 : 0001 : 0B23 : 2309 : 0000 : 0000 : 0000 : 00C1

# Finding the IPV6 prefix (global unicast address)

1. Typically, an enterprise requesting IPV6 address from their ISP will receive a /48 block.

2. Typically IPV6 subnets use a /64 prefix length

This means and enterprise has 16 bits to use to make subnets and remaining 64 bits can be used for hosts. 

2001 : 0DB8 : 8B00 : 0001 : 0000 : 0000 : 0000 : 0001 /64

To identify network address i have to divide by 4. 64 bits / 4 = 16 bits and 2001 : 0DB8 : 8B00 : 0001 is 16 bits which is network address

# 2001 : 0DB8 : 8B00 (48 bits global routing prefix assigned by ISP)

# 0001 ( 16 bits subnet identifier used by the enterprise to make various subnets)

# 0000 : 0000 : 0000 : 0001 (64 bits interface identifier the host portion of the address)

Finding the IPV6 prefix

1. 2001 : 0DB8 : 8B00 : 0001 : 0000 : 0000 : 0000 : 0001 /64 (simply make the second half of ip is 0)

2001 : 0DB8 : 8B00 : 1 :: 1

2. 300D (16) : 00F2 (32) : 0B34 (48) : 2100 : 0000 : 0000 : 1200 : 0001 /56

Ans : 300D : F2 : B34 : 2100 :: /56

3. 2001 : 0DB8 : 8B00 : 0001 : FB89 : 017B : 0020 : 0011 / 93

Ans : 2001 : DB8 : 8B00 : 1 : FB89 : 178 :: /93

017B -> 0d11 -> 0b1011 -> 0b1000 -> 0d8 -> 0 x 8

I can only use :: once.