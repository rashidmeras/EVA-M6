
Q1: What are Channels and Kernels (according to EVA)?

Kernels:
Kernels are basically a feature extractor that extracts information from a visual image. Each pixel in an image can be represented as a neuron and a kernel does an arithmetic operation on a group of neurons and creates new neuron as an output.

Channels:
A visual image can be considered to be split into different entities based on a specific feature and this entity is called a channel. For example we can split a visual image into three major colour components like Red, Green & Blue and call it as channels. Each channel highlights a specific feature in an image.  

Q2: Why should we only (well mostly) use 3x3 Kernels?
We use a 3x3 Kernels because of the following reason:
1. Using a 3x3 Kernel we look at a small portion of the image and it helps to capture complex features
2. Using a 3x3 Kernel we get lesser weights compared to other higher size Kernels
3. Using a 3x3 Kernel multiple times is more computationally efficient compared to Kernels of other size
4. The lowest size of a kernel can be 1x1 but using a 1x1 is like focussing on each pixel at a time and will not give information about its neghbouring pixels which could result in a bad output, hence 3x3 is just one step above 1x1 kernel and is much efficient in that perspective.
5. If we were to use an even Kernel and convolve from one layer to another let’s say layer1 to layer2, then all the pixels from layer1 would be symmetrical around layer2 if we use an even Kernel. This results into less distortion from layer1 to layer2 and this makes the network to learn much harder. Therefore by using a odd kernel like 3x3 this symmetry is broken and there is high distortion between layers and the network can learn much faster comparatively.

Q3: How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)

 1. => | 199 x 199 | 197 x 197 | 195 x 195 | 193 x 193 | 191 x 191 | 
 2. => | 189 x 189 | 187 x 187 | 185 x 185 | 183 x 183 | 181 x 181 |
 3. => | 179 x 179 | 177 x 177 | 175 x 175 | 173 x 173 | 171 x 171 |
 4. => | 169 x 169 | 167 x 167 | 165 x 165 | 163 x 163 | 161 x 161 |
 5. => | 159 x 159 | 157 x 157 | 155 x 155 | 153 x 153 | 151 x 151 |
 6. => | 149 x 149 | 147 x 147 | 145 x 145 | 143 x 143 | 141 x 141 |
 7. => | 139 x 139 | 137 x 137 | 135 x 135 | 133 x 133 | 131 x 131 |
 8. => | 129 x 129 | 127 x 127 | 125 x 125 | 123 x 123 | 121 x 121 |
 9. => | 119 x 119 | 117 x 117 | 115 x 115 | 113 x 113 | 111 x 111 |
10. => | 109 x 109 | 107 x 107 | 105 x 105 | 103 x 103 | 101 x 101 |
11. => |  99 x  99 |  97 x  97 |  95 x  95 |  93 x  93 |  91 x  91 |
12. => |  89 x  89 |  87 x  87 |  85 x  85 |  83 x  83 |  81 x  81 |
13. => |  79 x  79 |  77 x  77 |  75 x  75 |  73 x  73 |  71 x  71 |
14. => |  69 x  69 |  67 x  67 |  65 x  65 |  63 x  63 |  61 x  61 |
15. => |  59 x  59 |  57 x  57 |  55 x  55 |  53 x  53 |  51 x  51 |
16. => |  49 x  49 |  47 x  47 |  45 x  45 |  43 x  43 |  41 x  41 |
17. => |  39 x  39 |  37 x  37 |  35 x  35 |  33 x  33 |  31 x  31 |
18. => |  29 x  29 |  27 x  27 |  25 x  25 |  23 x  23 |  21 x  21 |
19. => |  19 x  19 |  17 x  17 |  15 x  15 |  13 x  13 |  11 x  11 |
20. => |   9 x   9 |   7 x   7 |   5 x   5 |   3 x   3 |   1 x   1 |

Total: 20 * 5 = 100 

Therefore in an image of 199x199, we need to do 3x3 convolution 100 times to reach to 1x1.
