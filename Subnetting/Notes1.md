# CIDR (Classless Inter Domain Routing)
Ip addresses are assigned to companies or organization by a non profit American Corporation called the IANA (The Internet Assigned Number Authority)

1. For example a very large company might recieve a class A or class B network (there are lots of available addresses to use for hosts in each class A and class B network), while a small company might recieve a class C network (there are fewer addresses in class C network).
However, this leads to many ip wasted

Company X needs ip addresses for 5000 end hosts.
A class C network doesnt provide enough addresses, so a class B network must be assigned.
This will result in about 60000 address being wasted.

# CIDR
1. When internet was first created, the creators did not predict that the internet would become as large as it is today.
2. This result in wasted address space like examples i showed you (there are many more examples) 
3. The IETF (Internet Engineer Task Force) introduced CIDR in 1993 to replace the "classful" addressing system.

With CIDR , the requirements of 
1. Class A = /8
2. Class B = /16
3. Class C = /24
were removed.
This allowed larger networks to be split into smaller networks, allowing greater efficiency.
This smaller networks are called "Subnetwork" or "Subnets"

# Subnet List

/8 = 255.0.0.0 → hosts: 16,777,214

/16 = 255.255.0.0 → hosts: 65,534

/24 = 255.255.255.0 → hosts: 254

/25 = 255.255.255.128 → hosts: 126

/26 = 255.255.255.192 → hosts: 62

/27 = 255.255.255.224 → hosts: 30

/28 = 255.255.255.240 → hosts: 14

/29 = 255.255.255.248 → hosts: 6

/30 = 255.255.255.252 → hosts: 2

/32 = 255.255.255.255 → hosts: 1 (single IP)

203.0.113.0/30 which is a subnet of a large class c network

11001011.00000000.01110001.00000000
11001011.00000000.01110001.00000001
11001011.00000000.01110001.00000010
11001011.00000000.01110001.00000011




CIDR	Mask (dec)	Last‑octet binary	Block size (last octet)	Total IPs	Usable hosts*
/25	255.255.255.128	10000000	128	128	126
/26	255.255.255.192	11000000	64	64	62
/27	255.255.255.224	11100000	32	32	30
/28	255.255.255.240	11110000	16	16	14
/29	255.255.255.248	11111000	8	8	6
/30	255.255.255.252	11111100	4	4	2
/31	255.255.255.254	11111110	2	2	0** (or 2)
/32	255.255.255.255	11111111	1	1	1


# Method

bit weights: 128  64  32  16   8   4   2   1
positions:   b7   b6   b5   b4  b3  b2  b1  b0



10000000 (only leftmost bit = 1) → 128
Calculation: 128 = 128

11000000 (left two bits = 1) → 128 + 64 = 192
Calculation: 128 + 64 = 192

11100000 (left three bits = 1) → 128 + 64 + 32 = 224
Calculation: 128 + 64 = 192; 192 + 32 = 224

11110000 (four 1s) → 128 + 64 + 32 + 16 = 240
Calculation: 128 + 64 = 192; 192 + 32 = 224; 224 + 16 = 240

11111000 (five 1s) → 128 + 64 + 32 + 16 + 8 = 248
Calculation: 240 + 8 = 248

11111100 (six 1s) → 128 + 64 + 32 + 16 + 8 + 4 = 252
Calculation: 248 + 4 = 252

11111110 (seven 1s) → 128 + 64 + 32 + 16 + 8 + 4 + 2 = 254
Calculation: 252 + 2 = 254

11111111 (eight 1s) → 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255
Calculation: 254 + 1 = 255