# 5) Menyelesaikan Persamaan dan Sistem Persamaan
Dalam subtopik ini, akan dibahas mengenai cara menyelesaikan persamaan
dan sistem persamaan.


# Persamaan

Persamaan adalah pernyataan bahwa dua ekspresi adalah sama. Persamaan
ditulis dengan tanda sama dengan (=).


Persamaan linear adalah persamaan yang tidak melibatkan sesuatu hasil
kali atau akar peubah. Semua peubah hanya terdapat sampai dengan angka
pertama dan tidak muncul sebagai argumen untuk fungsi trigonometrik,
fungsi logaritmik, atau untuk fungsi eksponensial.


Persamaan non-linier dapat diartikan sebagai persamaan yang tidak
mengandung syarat seperti persamaan linier, sehingga persamaan
non-linier dapat merupakan:


a. Persamaan yang memiliki pangkat selain satu (misal: x^2)


b. Persamaan yang mempunyai produk dua variabel (misal: xy)


Dalam penyelesaian persamaan non-linier diperlukan akar-akar persamaan
non-linier, dimana akar sebuah persamaan non-linier f(x) = 0 merupakan
nilai x yang menyebabkan nilai f(x) sama dengan nol.


## Persamaan Linear

Persamaan linear dengan satu variabel (PLSV) adalah suatu persamaan


yang memiliki satu variabel (peubah) dan pangkat tertingginya satu.


Persamaan linier satu variabel adalah persamaan yang ekuivalen dengan
salah satu bentuk


$$\boxed {ax+b=0}$$$$\text {dengan } a \text { dan } b \text { adalah bilangan real dan } a \neq 0$$Penyelesaian (solusi) dari suatu PLSV adalah bilangan real yang


menggantikan variabel sehingga persamaan tersebut menjadi bernilai
benar.


---

Persamaan linear dengan dua variabel (PLDV) adalah persamaan yang


memiliki dua peubah dan pangkat tertingginya satu.


Bentuk umumnya:


$$\boxed{ax+by=c; a\neq0; b\neq0}$$Penyelesaian (solusi) dari PLDV ax+by=c adalah bilangan terurut (x1,
y1) sedemikian hingga jika disubstitusikan x1 untuk x dan y1 untuk y


mengakibatkan persamaan menjadi bernilai benar.


Himpunan penyelesaian (HP) dari PLDV adalah himpunan semua bilangan


terurut (x1, y1) yang merupakan solusi dari PLDV tersebut.


---

Secara lebih umum, persamaan linear didefinisikan dalam n peubah x1,
x2, ..., xn sebagai persamaan yang dapat dinyatakan dalam bentuk


$$\boxed{a_{1}x_{1}+a_{2}x_{2}+...+a_{n}x_{n}=b}$$di mana a1, a2, ..., an dan b adalah konstanta-konstanta riil.


Pemecahan persamaan linear a1x1 + a1x2 + ... + anxn = b adalah urutan
dari n bilangan s1, s2, ..., sn sehingga persamaan tersebut dipenuhi
bila kita mensubstitusikannya terhadap x1=s1, x2=s2, ..., xn=sn.
Himpunan semua pemecahan persamaan tersebut dinamakan himpunan
pemecahan.


## Soal dan Penyelesaian Persamaan Linear

Soal No 1


Selesaikan persamaan berikut.


$$7(3x+6) = 11-(x+2)$$Penyelesaian :


Mendefinisikan persamaan


\>pl1 &= 7\*(3\*x+6)=11-(x+2); $&pl1 


$$7\,\left(3\,x+6\right)=9-x$$Menyelesaikan persamaan menggunakan fungsi solve(&lt;expr&gt;)


\>s1 &= solve(pl1); $&s1


$$\left[ x=-\frac{3}{2} \right] $$Function: solve


          solve (&lt;expr&gt;, &lt;x&gt;)


          solve (&lt;expr&gt;)


          solve ([&lt;eqn_1&gt;, ..., &lt;eqn_n&gt;], [&lt;x_1&gt;, ..., &lt;x_n&gt;])


Menyelesaikan persamaan aljabar &lt;expr&gt; untuk variabel &lt;x&gt; dan
mengembalikan daftar persamaan solusi di &lt;x&gt;. Jika &lt;expr&gt; bukan
persamaan, persamaan `&lt;expr&gt; = 0' diasumsikan sebagai gantinya. &lt;x&gt;
dapat dihilangkan jika &lt;expr&gt; berisi hanya satu variabel.


Mengecek penyelesaian dengan mensubstitusikannya ke persamaan


\>$&subst(s1, pl1) 


$$\frac{21}{2}=\frac{21}{2}$$Karena hasil substitusi s1 ke pl1 adalah 21/2 = 21/2, maka benar bahwa
x = -1.5 adalah solusi/penyelesaian untuk persamaan 7(3x+6) =
11-(x+2).


Penjelasan :


$$7(3x+6) = 11-(x+2)$$$$21x+42 = 9-x$$$$22x+33 = 0$$$$x = - \frac{33}{22} = - \frac{3}{2}$$---

Soal No 2


Selesaikan persamaan berikut untuk y.


$$3x+4y = 12$$Penyelesaian :


\>pl2 &= 3\*x+4\*y = 12; &powerdisp:true; $&pl2 // mendefinisikan persamaan


$$3\,x+4\,y=12$$\>s2 &= solve(pl2, y); $&s2 // menyelesaikan persamaan


$$\left[ y=\frac{12-3\,x}{4} \right] $$\>$&subst(s2, pl2) // mengecek penyelesaian


$$12=12$$Penjelasan :


$$3x+4y=12$$$$4y=12-3x$$$$y=\frac{12-3x}{4}$$Jadi, penyelesaian dari 3x+4y = 12, untuk y adalah


$$y=\frac{12-3x}{4}.$$---

Soal No 3


Carilah himpunan penyelesaian untuk persamaan berikut.


$$ x_{1}-4x_{2}+7x_{3}=5$$Penyelesaian :


Untuk mencari himpunan penyelesaian persamaan tersebut kita dapat
menetapkan sebarang nilai untuk setiap dua peubah dan menyelesaikan
persamaan tersebut untuk mencari peubah ketiga. Khususnya, jika kita
menetapkan nilai sebarang s dan t berturut-turut untuk x2 dan x3 dan
menyelesaikan persamaan tersebut untuk mencari x1, maka


\>x2 &= s; x3 &= t; pl3 &= x1-4\*x2+7\*x3=5; $&pl3 // mendefinisikan persamaan


$$-4\,s+7\,t+{\it x_1}=5$$\>s3 &= solve(pl3, x1); $&s3 // menyelesaikan persamaan


$$\left[ {\it x_1}=5+4\,s-7\,t \right] $$\>$&subst(s3, pl3) // mengecek penyelesaian


$$5=5$$Jadi, himpunan penyelesaian dari persamaan tersebut adalah


## Persamaan Kuadrat

Persamaan kuadrat merupakan persamaan matematika yang memuat variabel
dengan pangkat tertinggi dua. Persamaan kuadrat memiliki bentuk umum :


$$\boxed {ax^2+bx+c=0}$$$$\text {dengan } a, b, \text { dan } c \text { adalah bilangan real dan } a \neq 0$$Penyelesaian dari persamaan kuadrat disebut sebagai akar-akar
persamaan kuadrat. Macam akar persamaan kuadrat dapat diketahui dengan
mudah menggunakan rumus umum


$$\boxed{D = b^2-4ac}$$dari persamaan umum kuadrat.


Macam-macam akar persamaan kuadrat, yaitu :


1. Akar Real (D &gt; 0)


Jika nilai D &gt; 0 dari suatu persamaan kuadrat, maka akar-akar
persamaan kuadrat bernilai real namun memiliki akar-akar yang
berlainan. Dengan kata lain x1 tidak sama dengan x2.


2. Akar real sama, x1 = x2 (D = 0)


Merupakan jenis akar persamaan kuadrat yang menghasilkan akar-akar
bernilai sama.


3. Akar Imajiner / Tidak Real (D &lt; 0)


Jika nilai D &lt; 0 , maka akar dari persamaan kuadrat akan berbentuk
imajiner/ tidak real.


Untuk mencari penyelesaian persamaan kuadrat, terdapat beberapa metode
yang dapat digunakan, diantaranya yaitu faktorisasi, kuadrat sempurna,
dan menggunakan rumus ABC.


Berikut penjelasan mengenai beberapa metode untuk mencari penyelesaian
persamaan kuadrat.


1. Faktorisasi


Faktorisasi/pemfaktoran adalah suatu metode dalam menentukan akar-akar
dengan mencari nilai yang jika dikalikan maka akan menghasilkan nilai
lain.


Bentuk


$$x^2+bx+c=0$$

diubah kebentuk


$$(x-x_{1})(x-x_{2})=0$$Contoh:


$$x^2+5x+6=0$$$$(x+3)(x+2)=0$$$$x+3=0 \vee x+2=0$$$$x=-3 \vee x=-2$$2. Kuadrat Sempurna


Bentuk kuadrat sempurna merupakan bentuk persamaan kuadrat yang
menghasilkan bilangan rasional.


Bentuk


$$x^2+bx+c=0$$

diubah kebentuk


$$(x+p)^2=q$$Contoh:


$$x^2+4x+4=0$$$$(x+2)^2=0$$$$x+2=0$$$$x=-2$$3. Rumus Kuadrat ABC


Rumus abc merupakan alternatif pilihan ketika persamaan kuadrat sudah
tidak bisa diselesaikan dengan metode faktorisasi maupun kuadrat
sempurna.


Rumus :


$$\boxed{x_{1,2} = \frac{-b\pm\sqrt{b^2-4ac}}{2a}}$$## Soal dan Penyelesaian Persamaan Kuadrat

Soal No 1


Selesaikan


$$x^2+3x-28=0$$Penyelesaian :


\>pk1 &= x^2+3\*x-28=0; &powerdisp:false; $&pk1 // mendefinisikan persamaan


$$x^2+3\,x-28=0$$\>$&factor(pk1) // memfaktorkan persamaan


$$\left(x-4\right)\,\left(x+7\right)=0$$\>$&solve(pk1) // menyelesaikan persamaan


$$\left[ x=4 , x=-7 \right] $$Penjelasan :


$$x^2+3x-28=0$$$$(x-4)(x+7)=0$$$$x-4=0 \vee x+7=0$$$$x = 4 \vee x = -7$$Jadi, persamaan memiliki akar-akar persamaan kuadrat bernilai real
namun memiliki akar-akar yang berlainan, yaitu x = 4 atau x = -7.


\>a=1; b=3; c=-28; D = b^2 - 4\*a\*c // mengecek diskriminan


    121

D = 121 &gt; 0


maka benar persamaan akan memiliki akar-akar persamaan kuadrat
bernilai real namun memiliki akar-akar yang berlainan.


\>$&pk1 with x=4, $&pk1 with x=-7 // mengecek hasil penyelesaian


$$0=0$$$$0=0$$---

Soal No 2


Selesaikan


$$x^2+100=20x$$Penyelesaian :


\>pk2 &= x^2+100-20\*x=0; $&pk2 // mendefinisikan persamaan


$$x^2-20\,x+100=0$$\>$&factor(pk2) // memfaktorkan persamaan


$$\left(x-10\right)^2=0$$\>$&solve(pk2) // menyelesaikan persamaan


$$\left[ x=10 \right] $$\>a=1; b=20; c=100; D = b^2 - 4\*a\*c // mengecek diskriminan


    0

Karena diskriminan = 0 maka akar-akar bernilai sama.


\>$&pk2 with x=10 // mengecek hasil penyelesaian


$$0=0$$Penjelasan :


$$x^2+100=20x$$$$x^2-20x+100=0$$$$(x-10)^2=0$$$$x-10=0 \vee x-10=0$$$$x=10$$---

Soal No 3


Selesaikan


$$x^2+2x+2=0$$Penyelesaian :


\>pk3 &= x^2+2\*x+2=0; $&pk3 // mendefinisikan persamaan


$$x^2+2\,x+2=0$$\>$&factor(pk3) // memfaktorkan persamaan


$$x^2+2\,x+2=0$$\>spk3 &= solve(pk3); $&spk3 // menyelesaikan persamaan


$$\left[ x=-i-1 , x=i-1 \right] $$\>$&allroots(pk3) // menyelesaikan persamaan


$$\left[ x=1.0\,i-1.0 , x=-1.0\,i-1.0 \right] $$\>a=1; b=2; c=2; D = b^2 - 4\*a\*c // mengecek diskriminan


    -4

Karena diskriminan &lt; 0 maka akar imajiner/tidak real.


Penjelasan :


$$x^2+2x+2=0$$$$x_{1,2} = \frac{-b\pm\sqrt{b^2-4ac}}{2a}$$$$x_{1,2} = \frac{-2\pm\sqrt{2^2-4.1.2}}{2.1}$$$$x_{1,2} = \frac{-2\pm\sqrt{-4}}{2}$$$$x_{1,2} = \frac{-2\pm 2i}{2}$$$$x_{1} = -1+i$$$$x_{2} = -1-i$$## Persamaan Nilai Mutlak

Persamaan nilai mutlak adalah persamaan yang memuat variabel di dalam
tanda mutlak. Nilai mutlak biasa dituliskan dalam tanda mutlak |…|.
Misalnya, |4|, |5|, dan seterusnya. Jika suatu bilangan berada di
dalam tanda |...|, nilai bilangan itu bisa positif dan bisa juga
negatif. Namun, pemberian tanda mutlak menganggap bahwa nilainya
selalu positif. Contoh |x|=12 bisa bernilai x = -12 atau x = 12. Pada
persamaan nilai mutlak, ada dua kemungkinan persamaan yang memenuhi,
yaitu persamaan yang memuat tanda negatif maupun persamaan yang tidak
memuat tanda negatif.


$$\text {Untuk } a > 0 \text { dan ekspresi aljabar } X :$$$$\boxed {\left | X \right | = a \text { ekuivalen dengan } X = -a \text { atau } X = a.}$$## Soal dan Penyelesaian Persamaan Nilai Mutlak

Soal No 1


Selesaikan


$$\left | 4x-3 \right | +1=7$$Penyelesaian :


\>pnm1 &= abs(4\*x-3)+1=7; $&pnm1 // mendefinisikan persamaan


$$\left| 4\,x-3\right| +1=7$$\>$&solve(pnm1) // menyelesaikan persamaan


$$\left[ \left| 4\,x-3\right| =6 \right] $$\>$&solve(4\*x-3=6), $&solve(4\*x-3=-6) // menyelesaikan persamaan


$$\left[ x=\frac{9}{4} \right] $$$$\left[ x=-\frac{3}{4} \right] $$\>$&pnm1 with x=9/4, $&pnm1 with x=-3/4 // mengecek penyelesaian


$$7=7$$$$7=7$$Penjelasan :


$$\left | 4x-3 \right |+1=7$$$$\left | 4x-3 \right |=7-1$$$$\left | 4x-3 \right |=6$$Karena untuk a&gt;0 dan ekspresi aljabar X


$$\left | X \right |=a \text{ ekuivalen dengan } X = -a \text{ atau  } X=a$$maka


$$4x-3=6 \vee 4x-3=-6$$$$4x=9 \vee 4x=-3$$$$x=\frac{9}{4} \vee x=\frac{-3}{4}$$---

Soal No 2


Selesaikan


$$12-\left | x+6 \right |=5$$Penyelesaian :


\>pnm2 &= 12-abs(x+6)=5; $&pnm2 // mendefinisikan persamaan


$$12-\left| x+6\right| =5$$\>$&solve(pnm2) // menyelesaikan persamaan


$$\left[ \left| x+6\right| =7 \right] $$\>$&solve(x+6=7), $&solve(x+6=-7) // menyelesaikan persamaan


$$\left[ x=1 \right] $$$$\left[ x=-13 \right] $$\>$&pnm2 with x=1, $&pnm2 with x=-13 // mengecek penyelesaian


$$5=5$$$$5=5$$Penjelasan :


$$12-\left | x+6 \right |=5$$$$-\left | x+6 \right |=5-12$$$$\left | x+6 \right |=7$$Karena untuk a&gt;0 dan ekspresi aljabar X


$$\left | X \right |=a \text{ ekuivalen dengan } X = -a \text{ atau  } X=a$$maka


$$x+6=7 \vee x+6=-7$$$$x=1 \vee x=-13$$---

Soal No 3


Selesaikan


$$7-\left | 2x-1 \right |=6$$Penyelesaian :


\>pnm3 &= 7-abs(2\*x-1)=6; $&pnm3 // mendefinisikan persamaan


$$7-\left| 2\,x-1\right| =6$$\>$&solve(pnm3) // menyelesaikan persamaan


$$\left[ \left| 2\,x-1\right| =1 \right] $$\>$&solve(2\*x-1=1), $&solve(2\*x-1=-1) // menyelesaikan persamaan


$$\left[ x=1 \right] $$$$\left[ x=0 \right] $$\>$&pnm3 with x=1, $&pnm3 with x=0 // mengecek penyelesaian


$$6=6$$$$6=6$$Penjelasan :


$$7-\left | 2x-1 \right |=6$$$$-\left | 2x-1 \right |=6-7$$$$\left | 2x-1 \right |=1$$Karena untuk a&gt;0 dan ekspresi aljabar X


$$\left | X \right |=a \text{ ekuivalen dengan } X = -a \text{ atau  } X=a$$maka


$$2x-1=1 \vee 2x-1=-1$$$$2x=2 \vee 2x=0$$$$x=1 \vee x=0$$## Persamaan Eksponen

Persamaan eksponen adalah persamaan yang pangkatnya atau bilangan
pokok (basis) dan pangkatnya memuat suatu variabel.


Penyelesaian persamaan eksponen merupakan himpunan semua nilai x yang
memenuhi persamaan eksponen tersebut, atau bisa juga kita sebut
sebagai himpunan penyelesaian.


Bentuk-Bentuk Persamaan Eksponen


Persamaan Eksponen Sederhana


$$\text{1. Jika } a^{^{f(x)}} = 1 \text{, maka } f(x)=0 \text{ dengan } a>0 \text{ dan } a \neq 1$$$$\text{2. Jika } a^{^{f(x)}} = a^b \text{, maka } f(x)=b \text{ dengan } a>0 \text{ dan } a \neq 1$$$$\text{3. Jika } a^{^{f(x)}} = a^{^{g(x)}} \text{, maka } f(x)=g(x) \text{ dengan } a>0 \text{ dan } a \neq 1$$$$\text{4. Jika } a^{^{f(x)}} = b^{^{f(x)}} \text{, maka } f(x)=0 \text{ dengan } a,b>0 \text{ dan } a,b \neq 1$$$$\text{5. Jika } a^{^{f(x)}} = b^{^{g(x)}} \text{, maka } \log a^{^{f(x)}}=\log b^{^{g(x)}} \text{ dengan } a,b>0 \text{ dan } a,b \neq 1$$$$\text{6. Jika } f(x)^{^{g(x)}} = 1 \text{, maka ada tiga langkah penyelesaian, yaitu:}$$$$\text{a. } f(x)=1$$$$\text{b. } f(x)=-1 \text{, syarat } g(x) \text{ genap}$$$$\text{c. }g(x)=0 \text{, syarat } f(x) \neq 0$$$$\text{7. Jika } f(x)^{^{h(x)}} = g(x)^{^{h(x)}} \text{, maka ada tiga langkah penyelesaian, yaitu:}$$$$\text{a. }f(x)=g(x)$$$$\text{b. }f(x)=-g(x) \text{, syarat } h(x) \text{ genap}$$$$\text{c. }h(x)=0 \text{, syarat } f(x),g(x) \neq 0$$$$\text{8. Jika } f(x)^{^{g(x)}} = f(x)^{^{h(x)}} \text{, maka ada empat langkah penyelesaian, yaitu:}$$$$\text{a. }g(x)=h(x)$$$$\text{b. }f(x)=1$$$$\text{c. }f(x)=-1 \text{, syarat } g(x) \text{ dan } h(x) \text{ genap atau ganjil}$$$$\text{d. }f(x)=0 \text{, syarat } g(x) \text{ dan } h(x) \text{ positif}$$Persamaan Eksponen Tak Sederhana


$$\text{1. Jika } p(a^x)^2+q(a^x)+r=0 \text{, maka ada dua langkah penyelesaian, yaitu:}$$$$\text{a. Misalkan } a^x \text{ dengan variabel lain (selain variabel pada soal)}$$$$\text{b. Faktorkan persamaan}$$## Soal dan Penyelesaian Persamaan Eksponen

Soal No 1


Selesaikan


$$3^x = 81$$Penyelesaian :


\>pe1 &= 3^x=81; $&pe1 // mendefinisikan persamaan


$$3^{x}=81$$\>$&solve(pe1) // menyelesaikan persamaan


$$\left[ x=\frac{\log 81}{\log 3} \right] $$\>x=log(81)/log(3) // menyelesaikan persamaan


    4

Menggunakan solve tidak langsung menemukan hasil akhir sehingga kita
bisa menggunakan find_root


\>$&find\_root(pe1,x,0,10) // menyelesaikan persamaan


$$4.0$$\>$&pe1 with x=4 // mengecek penyelesaian


$$81=81$$Penjelasan :


$$3^x =81$$$$3^x = 3^4$$$$x=4$$---

Soal No 2


Selesaikan


$$4^{^{3x-5}}=16$$Penyelesaian :


\>pe2 &= 4^(3\*x-5)=16; $&pe2 // mendefinisikan persamaan


$$4^{3\,x-5}=16$$\>$&solve(pe2) // menyelesaikan persamaan


$$\left[ x=\frac{\log 16+5\,\log 4}{3\,\log 4} \right] $$\>x=(logbase(16, 4)+5\*logbase(4, 4))/3\*logbase(4, 4), frac(x) // menyelesaikan persamaan


    2.33333333333
    7/3

Menggunakan solve tidak langsung menemukan hasil akhir sehingga kita
bisa menggunakan find_root


\>$&find\_root(pe2,x,0,10) // menyelesaikan persamaan


$$2.333333333333333$$\>$&pe2 with x=7/3 // mengecek penyelesaian


$$16=16$$Penjelasan :


$$4^{^{3x-5}} = 16$$$$4^{^{3x-5}} = 4^2$$$$3x-5 = 2$$$$3x = 7$$$$x = \frac{7}{3}$$cara lain :


$$4^{^{3x-5}} = 16$$$$(3x-5)\log_{4}4 = \log_{4}16$$$$x = \frac{\log_{4}16 + 5\log_{4}4}{3\log_{4}4}$$$$x = \frac{2 + 5}{3}$$$$x = \frac{7}{3}$$---

Soal No 3


Selesaikan


$$5^{^{x+2}} = 4^{^{1-x}}$$Penyelesaian :


\>pe3 &= 5^(x+2)= 4^(1-x); $&pe3 // mendefinisikan persamaan


$$5^{x+2}=4^{1-x}$$\>$&solve(pe3) // menyelesaikan persamaan


$$\left[ 5^{x+2}=4^{1-x} \right] $$Karena tidak terselesaikan, kita ubah menjadi bentuk logaritma.


\>$&solve(log(5^(x+2))=log(4^(1-x))) // menyelesaikan persamaan


$$\left[ x=\frac{\log 4-2\,\log 5}{\log 5+\log 4} \right] $$\>x = (log(4)-2\*log(5))/(log(5)+log(4)) // menyelesaikan persamaan


    -0.611730721041

Menggunakan solve tidak langsung menemukan hasil akhir sehingga kita
bisa menggunakan find_root


\>$&find\_root(pe3,x,-0.7,10) // menyelesaikan persamaan


$$-0.611730721041445$$\>$&pe3 with x=-0.611730721041445 // mengecek penyelesaian


$$9.340251790952284=9.340251790952284$$Penjelasan :


$$5^{^{x+2}} = 4^{^{1-x}}$$$$\log_{5} 5^{^{x+2}} = \log_{5} 4^{^{1-x}}$$$$x+2 = \log_{5} 2^{^{2-2x}}$$$$x+2 = (2-2x) \log_{5} 2$$$$x+2 = 2\log_{5}2 - 2\log_{5}2 x$$$$x+2\log_{5}2 x = 2\log_{5}2 -2$$$$x(1+2\log_{5}2) = 2\log_{5}2 -2$$$$x = \frac{2\log_{5}2 -2}{1+2\log_{5}2}$$$$x = \frac{\log_{5}2^2 +\log_{5}5^{^{-2}}}{\log_{5}5+\log_{5}2^2}$$$$x = \frac{\log_{5}(2^2.5^{^{-2}})}{\log_{5}(5.2^2)}$$$$x = \frac{\log_{5}(\frac{4}{25})}{\log_{5}20}$$$$x = \log_{20}(\frac{4}{25})$$$$x = \log_{20}(\frac{2}{5})^2$$$$x = 2\log_{20}(\frac{2}{5}) = -0,611731$$## Persamaan Logaritma

Persamaan logaritma adalah persamaan yang memuat bentuk logaritma
dengan basis atau numerus, atau keduanya memuat variabel. Hal tersebut
berarti ada dua bentuk logaritma (di ruas kiri dan kanan) dimana basis
atau numerus atau keduanya memuat variabel, kemudian kedua ruas ini
dihubungan dengan tanda sama dengan. Nilai x yang memenuhi persamaan
ini disebut dengan penyelesaian dari persamaan tersebut.


Bentuk umum logaritma :


$$\boxed{\log_{a} x = n}$$$$a \text{ = basis atau bilangan pokok, dengan syarat }a > 0 \text { dan } a \neq 1$$$$x \text{ = numerus, dengan syarat } x > 0$$$$n \text{ = nilai logaritma}$$Bentuk-bentuk persamaan logaritma :


Bentuk Pertama


$$\log_{a} f(x) = \log_{a} n \Leftrightarrow f(x)=n$$$$\text{dengan syaratnya : } a,n,f(x)>0 \text{ dan } a \neq 1$$Bentuk Kedua


$$\log_{a} f(x) = \log_{a} g(x) \Leftrightarrow f(x)=g(x)$$$$\text{dengan syaratnya : } a,f(x),g(x)>0 \text{ dan } a \neq 1$$Bentuk Ketiga


$$\log_{a} f(x) = \log_{b} f(x) \Leftrightarrow f(x)=1$$$$\text{dengan syaratnya : } a,b,f(x)>0 \text{, } a,b \neq 1 \text{, dan } a \neq b$$Bentuk Keempat


$$\log_{f(x)} g(x) = \log_{f(x)} h(x) \Leftrightarrow g(x)=h(x)$$$$\text{dengan syaratnya : } f(x),g(x),h(x)>0 \text{ dan } f(x) \neq 1$$Bentuk Kelima


$$\log_{f(x)} h(x) = \log_{g(x)} h(x) \Leftrightarrow f(x)=g(x)$$$$\text{dengan syaratnya : } f(x),g(x),h(x)>0 \text{ dan } f(x),g(x) \neq 1$$Bentuk Keenam


$$A(\log_{a} f(x))^2 + B(\log_{a} f(x))+C=0$$$$\text{dengan syaratnya : } a,f(x)>0 \text{ dan } a \neq 1$$## Soal dan Penyelesaian Persamaan Logaritma

Soal No 1


Selesaikan


$$\log x = -4$$Penyelesaian :


\>plog1 &= log(x)=-4; $&plog1 // mendefinisikan persamaan


$$\log x=-4$$\>slog1 &= solve(plog1); $&slog1 // menyelesaikan persamaan


$$\left[ x=e^ {- 4 } \right] $$\>$&subst(slog1,plog1) // mengecek penyelesaian


$$-4=-4$$Penjelasan :


Logaritma memiliki basis e (menggunakan bilangan Euler), maka :


$$\log x = -4$$

karena


$$\log_{a} x = n \Leftrightarrow a^n = x$$

maka :


$$x = e^{-4}$$---

Soal No 2


Selesaikan


$$\log_{5} x = 4$$Penyelesaian :


\>plog2 &= log(x)/log(5) = 4; $&plog2 // mendefinisikan persamaan


$$\frac{\log x}{\log 5}=4$$Karena fungsi: log (&lt;x&gt;) mewakili logaritma natural (basis e) dari &lt;x&gt;
dan Maxima tidak memiliki fungsi bawaan untuk logaritma basis 10 atau
pangkalan lainnya, maka logaritma basis 10 dapat ditulis :


`log10(x) := log(x) / log(10)'


begitu juga pangkalan lainnya.


\>$&solve(plog2) // menyelesaikan persamaan


$$\left[ x=625 \right] $$Mengecek penyelesaian


\>log(625)/log(5)


    4

Penjelasan :


$$\log_{5}x=4$$$$\frac{\log x}{\log 5} = 4$$$$\log x = 4 \log 5$$$$\log x = \log 5^4$$$$x = 5^4$$$$x = 625$$## Persamaan Trigonometri

Jika suatu persamaan berisi ekspresi trigonometri dengan variabel,
seperti cos(x), itu disebut sebagai persamaan trigonometri. Beberapa
persamaan trigonometri adalah identitas, seperti


$$sin^2 x+cos^2 x=1$$

Seperti jenis persamaan lainnya, persamaan trigonometri diselesaikan
dengan mencari semua nilai x yang membuat persamaan tersebut benar.


Jenis Persamaan Trigonometri


1. Persamaan sinus


$$\sin(x) = \sin(a)$$$$x = a + 2\pi k$$$$x = (\pi-a)+2\pi k$$

Untuk k merupakan konstanta bilangan bulat.


2. Persamaan Cosinus


$$\cos(x) = \cos(a)$$$$x = \pm a + 2\pi k$$

Untuk k merupakan konstanta bilangan bulat.


3. Persamaan Tangen


$$\tan(x) = \tan(a)$$$$x = a + 2\pi k$$

Untuk k merupakan konstanta bilangan bulat.


## Soal dan Penyelesaian Persamaan Trigonometri

Soal No 1


Selesaikan dan temukan semua solusi di [0,2pi)


$$2\cos(x)^2 =1$$Penyelesaian :


\>&load(to\_poly\_solve)


    
            D:/SOFTWARE APKOM/Euler x64/maxima/share/maxima/5.35.1/share/\
    to_poly_solve/to_poly_solve.mac
    

Function: load (&lt;filename&gt;)


Mengevaluasi ekspresi dalam &lt;filename&gt;, sehingga membawa variabel,
fungsi, dan objek lain ke dalam Maxima.


\>pt1 &= 2\*cos(x)^2=1; $&pt1 // mendefinisikan persamaan


$$2\,\cos ^2x=1$$\>spt1 &= nicedummies(to\_poly\_solve(pt1, x)); $&spt1 // menyelesaikan persamaan


$$\left[ x=\frac{2\,\pi\,{\it \%z_0}-\frac{\pi}{2}}{2} \right]  \cup 
 \left(\left[ x=\frac{2\,\pi\,{\it \%z_1}+\frac{\pi}{2}}{2} \right] 
 \right)$$\>$&sublis([%z0=0, %z1=0],spt1), $&sublis([%z0=1, %z1=1],spt1), ...  
\>   $&sublis([%z0=2, %z1=2],spt1) // menyelesaikan persamaan dengan mensubstitusikan bilangan bulat


$$\left[ x=-\frac{\pi}{4} \right]  \cup \left(\left[ x=\frac{\pi}{4}
  \right] \right)$$$$\left[ x=\frac{3\,\pi}{4} \right]  \cup \left(\left[ x=\frac{5\,\pi
 }{4} \right] \right)$$$$\left[ x=\frac{7\,\pi}{4} \right]  \cup \left(\left[ x=\frac{9\,\pi
 }{4} \right] \right)$$Penjelasan :


$$2\cos(x)^2 = 1$$$$\cos(x)^2 = \frac{1}{2}$$$$\cos(x) = \pm \frac{\sqrt{2}}{2}$$$$x = \pm \frac{\pi}{4} + 2\pi k \vee x = \pm \frac{3\pi}{4} + 2\pi k$$Karena solusi di [0,2pi) maka solusi/penyelesaiannya:


$$x = \frac{\pi}{4}, \frac{3\pi}{4}, \frac{5\pi}{4}, \frac{7\pi}{4}$$# Sistem Persamaan

Sistem persamaan adalah dua atau lebih persamaan yang mengandung
variabel yang sama. Dalam sistem persamaan, penyelesaiannya harus
memenuhi semua persamaan dalam sistem.


## Sistem Persamaan Linear

Sistem persamaan linear adalah persamaan-persamaan linear yang
dikorelasikan untuk membentuk suatu sistem. Sistem Persamaan Linier
(SPL) dengan n variabel x1, x2, …, xn dan m persamaan adalah suatu
sistem persamaan yang berbentuk


$$a_{11}x_{1}+a_{12}x_{2}+... a_{1j}x_{j}+...+a_{1n}x_{n}=b_{1}$$$$a_{21}x_{1}+a_{22}x_{2}+... a_{2j}x_{j}+...+a_{2n}x_{n}=b_{2}$$$$\text{.}$$$$\text{.}$$$$\text{.}$$$$a_{m1}x_{1}+a_{m2}x_{2}+...a_{mj}x_{j}+...+a_{mn}x_{n}=b_{m}$$$$\text{dengan } a_{ij} \in \mathbb{R}, i=1,2,...,m \text{ dan } j=1,2,...,n.$$Selesaian (solusi) dari System Persamaan Linear diatas adalah pasangan
n-bilangan terurut (s1, s2, …, sn) yang jika s1 disubstitusikan ke x1,
s2 disubstitusikan ke x2, …, sn disubstitusikan ke xn maka berlaku
ai1.s1 + ai2.s2 + … + ain.sn = bi, i=1,2, …, m


Secara lengkap, jika (s1, s2, …, sn) dari SPL diatas maka (s1, s2, …,
sn) merupakan solusi dari setiap persamaan dalam SPL diatas. Artinya


berlaku


$$a_{11}s_{1}+a_{12}s_{2}+... a_{1j}s_{j}+...+a_{1n}s_{n}=b_{1}$$$$a_{21}s_{1}+a_{22}s_{2}+... a_{2j}s_{j}+...+a_{2n}s_{n}=b_{2}$$$$\text{.}$$$$\text{.}$$$$\text{.}$$$$a_{m1}s_{1}+a_{m2}s_{2}+...a_{mj}s_{j}+...+a_{mn}s_{n}=b_{m}$$Himpunan semua selesaian dari Sistem Persamaan Linier disebut Himpunan
Solusi (Notasinya HS).


Sistem Persamaan Linier yang mempunyai selesaian disebut Konsisten dan
Sistem yang tidak mempunyai selesaian disebut tidak konsisten.


Untuk melihat tafsiran geometri dari selesaian suatu SPL,


diberikan SPL dengan 2 persamaan dan 2 variabel, sebagai berikut :


dengan a1, a2, b1, dan b2 konstanta riil tidak nol.


Grafik persamaan-persamaan ini merupakan garis, misal garis l1


dan garis l2. Karena titik (x,y) terletak pada sebuah garis jika dan


hanya jika bilangan-bilangan x dan y memenuhi persamaan tersebut,


maka selesaian SPL tersebut akan bersesuaian dengan titik perpotongan
dari garis l1 dan garis l2. Terdapat 3 (tiga) kemungkinan, yaitu :


a. garis l1 dan garis l2 sejajar, yaitu jika tidak terdapat titik


perpotongan sehingga sistem tidak mempunyai selesaian.


b. garis l1 dan garis l2 berpotongan pada satu titik, sehingga sistem
hanya mempunyai satu (tunggal) selesaian.


c. garis l1 dan garis l2 berimpit artinya terdapat takterhingga banyak
titik perpotongan. Dalam hal ini sistem mempunyai takterhingga banyak
selesaian. Biasa dikatakan SPL mempunyai banyak solusi.


Berdasarkan ilustrasi kasus di atas, maka SPL mempunyai tiga
kemungkinan yang berkaitan dengan selesaian, yaitu tidak mempunyai
selesaian, mempunyai satu selesaian dan mempunyai takterhingga banyak
selesaian.


Metode Penyelesaian Sistem Persamaan Linear


1) Operasi Persamaan Linier (OPL)


Metode dasar untuk menyelesaikan suatu SPL adalah mengganti sistem
yang diberikan dengan sistem baru. Sistem baru yang mempunyai himpunan
selesaian (HS) sama, dengan pemecahan yang lebih mudah. Sistem baru
ini diperoleh dari suatu tahapan dengan menerapkan suatu langkah
operasi. Operasi-operasi yang dilakukan dimaksudkan untuk
menghilangkan variabel-variabel secara sistematis.


Operasi Persamaan Linier (OPL) tersebut adalah


1.mengalikan suatu persamaan dengan skalar riil tidak nol, k


2.menukar letak dua persamaan


3.mengganti suatu pers. dengan pers. tsb + k kali pers. lain


2) Operasi Baris Elementer (OBE)


Operasi-operasi yang digunakan untuk menyelesaikan SPL melalui [A|B]
adalah Operasi Baris Elementer (OBE). OBE adalah suatu operasi yang
hanya melibatkan unsure (bilangan) dalam suatu matriks.


3) Eliminasi Gauss dan Eliminasi Gauss-Jordan


Telah diketahui bahwa setiap SPL dapat diselesaikan dengan mengubah
matriks lengkapnya menjadi suatu matriks tertentu sehingga
selesaiannya dapat segera diperoleh. Maka kecepatan dalam
menyelesaikan SPL tergantung pada proses pengubahan matriks lengkap ke
bentuk matriks yang spesifik. Matriks spesifik yang dimaksud adalah
MEB atau MEBT.


Proses perubahan matriks lengkap [A|B] ke bentuk MEB dengan OBE
disebut Eliminasi Gauss. Sedangkan proses perubahan matriks lengkap
[A|B] ke bentuk MEBT melalui OBE dinamakan Eliminasi Gauss-Jordan.


4) Metode Invers Matriks


Metode Invers menggunakan matriks balikan dari A. Sistem Persamaan
Linier Ax = b dapat diselesaikan dengan cara x = (A invers) dikalikan
b dengan syarat (A invers) ada.


5) Metode Dekomposisi LU


Jika matriks A persegi non-singular maka ia dapat difaktorkan (di
dekomposisi) menjadi matriks segitiga bawah L (lower) dan matriks
segitiga atas U (upper).


## Soal dan Penyelesaian Sistem Persamaan Linear

Soal No 1


Selesaikan sistem persamaan linear berikut.


$$4x+2y=11,$$$$3x-y=2$$Penyelesaian :


\>spl1a &= 4\*x+2\*y = 11; spl1b &= 3\*x-y=2; $&spl1a, $&spl1b // mendefinisikan SPL


$$2\,y+4\,x=11$$$$3\,x-y=2$$\>sspl1 &= solve([spl1a,spl1b],[x,y]); $&sspl1 // menyelesaikan SPL


$$\left[ \left[ x=\frac{3}{2} , y=\frac{5}{2} \right]  \right] $$\>$&subst(sspl1,spl1a), $&subst(sspl1,spl1b) // mengecek penyelesaian


$$11=11$$$$2=2$$Metode grafik :


\>plot2d(["(11-4\*x)/2", "-2+3x"], -1, 4, grid = 8, color=4:5):


![images/Aljabar_5%20Menyelesaikan%20Persamaan%20dan%20Sistem%20Persamaan-251.png](images/Aljabar_5%20Menyelesaikan%20Persamaan%20dan%20Sistem%20Persamaan-251.png)

Karena garis persamaan 4x + 2y = 11 dan 3x - y = 2 berpotongan pada
satu titik, maka sistem hanya mempunyai satu penyelesaian.


\>A1 = [4,2;3,-1]


                4             2 
                3            -1 

\>b1 = [11;2]


               11 
                2 

\>M1 = A1|b1


                4             2            11 
                3            -1             2 

Metode matriks dengan Eliminasi Gauss-Jordan :


\>echelon(M1)


                1             0           1.5 
                0             1           2.5 

Metode invers :


\>inv(A1).b1


              1.5 
              2.5 

Metode LU Decomposition :


\>ASPL1 &= matrix([4,2],[3,-1]); bspl1 &= matrix([11],[2]); $&ASPL1, $&bspl1, ...  
\>   $&linsolve\_by\_lu(ASPL1, bspl1)


$$\begin{pmatrix}4 & 2 \\ 3 & -1 \\ \end{pmatrix}$$$$\begin{pmatrix}11 \\ 2 \\ \end{pmatrix}$$$$\left[ \begin{pmatrix}\frac{3}{2} \\ \frac{5}{2} \\ \end{pmatrix}
  , \mathbf{false} \right] $$Dari berbagai metode penyelesaian yang sudah dilakukan dapat dilihat
bahwa SPL tersebut memiliki satu penyelesaian, yaitu x = 1.5 dan y =
2.5


---

Soal No 2


Selesaikan sistem persamaan linear berikut.


$$3x+2y+2z=3,$$$$x+2y-z=5,$$$$2x-4y+z=0$$Penyelesaian :


\>spl2a &= 3\*x+2\*y+2\*z=3; spl2b &= x+2\*y-z=5; spl2c &= 2\*x-4\*y+z=0; // mendefinisikan SPL

\>&powerdisp:true; $&spl2a, $&spl2b, $&spl2c // mendefinisikan SPL


$$3\,x+2\,y+2\,z=3$$$$x+2\,y-z=5$$$$2\,x-4\,y+z=0$$\>sspl2 &= solve([spl2a,spl2b,spl2c],[x,y,z]); $&sspl2 // menyelesaikan SPL


$$\left[ \left[ x=2 , y=\frac{1}{2} , z=-2 \right]  \right] $$\>$&subst(sspl2,spl2a), $&subst(sspl2,spl2b), $&subst(sspl2,spl2c) // mengecek penyelesaian


$$3=3$$$$5=5$$$$0=0$$\>A2 = [3,2,2;1,2,-1;2,-4,1]


                3             2             2 
                1             2            -1 
                2            -4             1 

\>b2 = [3;5;0]


                3 
                5 
                0 

\>M2 = A2|b2


                3             2             2             3 
                1             2            -1             5 
                2            -4             1             0 

Metode matriks dengan Eliminasi Gauss-Jordan :


\>echelon(M2)


                1             0             0             2 
                0             1             0           0.5 
                0             0             1            -2 

Metode invers :


\>inv(A2).b2


                2 
              0.5 
               -2 

Metode LU Decomposition :


\>ASPL2 &= matrix([3,2,2],[1,2,-1],[2,-4,1]); bspl2 &= matrix([3],[5],[0]); $&ASPL2, $&bspl2, ...  
\>   $&linsolve\_by\_lu(ASPL2, bspl2)


$$\begin{pmatrix}3 & 2 & 2 \\ 1 & 2 & -1 \\ 2 & -4 & 1 \\ 
 \end{pmatrix}$$$$\begin{pmatrix}3 \\ 5 \\ 0 \\ \end{pmatrix}$$$$\left[ \begin{pmatrix}2 \\ \frac{1}{2} \\ -2 \\ \end{pmatrix} , 
 \mathbf{false} \right] $$Dari berbagai metode penyelesaian yang sudah dilakukan dapat dilihat
bahwa SPL tersebut memiliki satu penyelesaian, yaitu x = 2, y = 0.5,
dan z = -2


---

Soal No 3


Selesaikan sistem persamaan linear berikut


$$3x_{1}-2x_{2}+3x_{3}+2x_{4}=10,$$$$2x_{1}+3x_{2}-x_{3}+x_{4}=6,$$$$x_{1}-5x_{2}+4x_{3}+x_{4}=4$$Penyelesaian :


\>remvalue x3,x2

\>spl3a &= 3\*x1-2\*x2+3\*x3+2\*x4=10; spl3b &= 2\*x1+3\*x2-x3+x4=6; ...  
\>   spl3c &= x1-5\*x2+4\*x3+x4=4; $&spl3a, $&spl3b, $&spl3c // mendefinisikan SPL


$$3\,{\it x_1}-2\,{\it x_2}+3\,{\it x_3}+2\,{\it x_4}=10$$$$2\,{\it x_1}+3\,{\it x_2}-{\it x_3}+{\it x_4}=6$$$${\it x_1}-5\,{\it x_2}+4\,{\it x_3}+{\it x_4}=4$$\>$&solve([spl3a,spl3b,spl3c], [x1,x2,x3,x4]) // menyelesaikan SPL


$$\left[ \left[ {\it x_1}=\frac{42-8\,{\it \%r_3}-7\,{\it \%r_4}}{13}
  , {\it x_2}=\frac{-2+{\it \%r_3}+9\,{\it \%r_4}}{13} , {\it x_3}=
 {\it \%r_4} , {\it x_4}={\it \%r_3} \right]  \right] $$\>A3 = [3,-2,3,2;2,3,-1,1;1,-5,4,1]


                3            -2             3             2 
                2             3            -1             1 
                1            -5             4             1 

\>b3 = [10;6;4]


               10 
                6 
                4 

\>M3 = A3|b3


                3            -2             3             2            10 
                2             3            -1             1             6 
                1            -5             4             1             4 

Metode matriks dengan Eliminasi Gauss-Jordan :


\>echelon(M3)


                1             0      0.538462      0.615385       3.23077 
                0             1     -0.692308    -0.0769231     -0.153846 

Karena ada satu baris dengan semua elemen nol di sisi kiri (koefisien
variabel) dan elemen paling kanan (hasil) juga nol, maka sistem
memiliki solusi tak tentu dengan banyak solusi. Ini berarti terdapat
variabel bebas yang dapat diatur secara bebas.


Jika dimisalkan x3 = s dan x4 = t dengan s, t bilangan riil, maka:


$$x_{1} = \frac{42-7s-8t}{13}$$$$x_{2} = \frac{-2+9s+t}{13}$$$$x_{3} = s$$$$x_{4} = t$$Jadi,


$$HS = \begin{Bmatrix}(\frac{42-7s-8t}{13}, \frac{-2+9s+t}{13}, s, t)/s,t \in \mathbb{R}\end{Bmatrix}$$---

Soal No 4


Selesaikan SPL berikut


$$4x-3y=10,$$$$-x+3y=-3,$$$$3x=10$$Penyelesaian :


\>spl4a &= 4\*x-3\*y=10; spl4b &= -x+3\*y=-3; spl4c &= 3\*x=10;  ...  
\>   $&spl4a, $&spl4b, $&spl4c // mendefinisikan SPL


$$4\,x-3\,y=10$$$$-x+3\,y=-3$$$$3\,x=10$$\>$&solve([spl4a,spl4b,spl4c], [x,y]) // menyelesaikan SPL


$$\left[  \right] $$Tidak ada solusi yang memenuhi


\>A4 = [4,-3;-1,3;3,0]


                4            -3 
               -1             3 
                3             0 

\>b4 = [10;-3;10]


               10 
               -3 
               10 

\>M4 = A4|b4


                4            -3            10 
               -1             3            -3 
                3             0            10 

Metode matriks dengan Eliminasi Gauss-Jordan :


\>echelon(M4)


                1             0             0 
                0             1             0 
                0             0             1 

Karena ada baris yang memiliki semua elemen nol kecuali elemen paling
kanan, seperti [0 0 | k], di mana k bukan nol, maka sistem tidak
memiliki solusi. Ini berarti sistem persamaan tidak konsisten dan
tidak memiliki solusi yang memenuhi semua persamaan.


## Sistem Persamaan Non Linear

Sistem persamaan nonlinier adalah sistem yang terdiri dari dua atau
lebih persamaan dalam dua variabel atau lebih yang mengandung paling
sedikit satu persamaan yang tidak linier.


Menyelesaikan Sistem Persamaan Nonlinier Menggunakan Substitusi


Metode substitusi yang kita gunakan untuk sistem linier adalah metode
yang sama yang akan kita gunakan untuk sistem nonlinier. Kita
menyelesaikan satu persamaan untuk satu variabel dan kemudian
mensubstitusikan hasilnya ke persamaan kedua untuk menyelesaikan
variabel lain, dan seterusnya. Namun, terdapat variasi dalam hasil
yang mungkin terjadi.


Menyelesaikan Sistem Persamaan Nonlinier Menggunakan Eliminasi


Substitusi sering kali merupakan metode yang disukai ketika sistem
persamaan mencakup persamaan linier dan persamaan nonlinier. Namun,
jika kedua persamaan dalam sistem mempunyai variabel derajat kedua
yang serupa, penyelesaiannya menggunakan eliminasi dengan penjumlahan
seringkali lebih mudah daripada substitusi. Secara umum, eliminasi
adalah metode yang jauh lebih sederhana ketika sistem hanya melibatkan
dua persamaan dalam dua variabel (sistem dua-dua), dibandingkan sistem
tiga-tiga, karena langkah-langkahnya lebih sedikit.


## Soal dan Penyelesaian Sistem Persamaan Non Linear

Soal No 1


Selesaikan sistem persamaan non linear berikut.


$$3x-y=-2,$$$$2x^2-y=0$$Penyelesaian :


\>spnl1a &= 3\*x-y=-2; spnl1b &= 2\*x^2-y=0; $&spnl1a, $&spnl1b // mendefinisikan SPNL


$$3\,x-y=-2$$$$2\,x^2-y=0$$\>$&solve([spnl1a,spnl1b],[x,y]) // menyelesaikan SPNL


$$\left[ \left[ x=2 , y=8 \right]  , \left[ x=-\frac{1}{2} , y=\frac{
 1}{2} \right]  \right] $$Metode grafik :


\>plot2d(["3\*x+2", "2\*x^2"], -2, 3, grid = 8, color=4:5): 


![images/Aljabar_5%20Menyelesaikan%20Persamaan%20dan%20Sistem%20Persamaan-292.png](images/Aljabar_5%20Menyelesaikan%20Persamaan%20dan%20Sistem%20Persamaan-292.png)

Berpotongan di dua titik berarti memiliki dua penyelesaian.


Jadi, SPNL tersebut memiliki dua penyelesaian, yaitu (2,8) dan
(-0.5,0.5)


---

Soal No 2


Selesaikan sistem persamaan non linear berikut.


$$2x^2+y=3,$$$$3x^2+y=4$$Penyelesaian :


\>spnl2a&= 2\*x^2+y=3; spnl2b &= 3\*x^2+y=4; $&spnl2a, $&spnl2b // mendefinisikan SPNL


$$2\,x^2+y=3$$$$3\,x^2+y=4$$\>$&solve([spnl2a,spnl2b], [x,y]) // menyelesaikan SPNL


$$\left[ \left[ x=-1 , y=1 \right]  , \left[ x=1 , y=1 \right] 
  \right] $$Metode grafik :


\>plot2d(["-2\*x^2+3", "-3\*x^2+4"], -2, 2, grid = 8, color=4:5):


![images/Aljabar_5%20Menyelesaikan%20Persamaan%20dan%20Sistem%20Persamaan-298.png](images/Aljabar_5%20Menyelesaikan%20Persamaan%20dan%20Sistem%20Persamaan-298.png)

Berpotongan di dua titik berarti memiliki dua penyelesaian.


Jadi, SPNL tersebut memiliki dua penyelesaian, yaitu (-1,1) dan (1,1).


