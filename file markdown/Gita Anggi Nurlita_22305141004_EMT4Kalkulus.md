# Gita Anggi Nurlita_22305141004_EMT4Kalkulus
Nama : Gita Anggi Nurlita


NIM : 22305141004


Kelas : Matematika B


# Kalkulus dengan EMT

Materi Kalkulus mencakup di antaranya:


* 
Fungsi (fungsi aljabar, trigonometri, eksponensial, logaritma,
* komposisi fungsi)

* 
Limit Fungsi,

* 
Turunan Fungsi,

* 
Integral Tak Tentu,

* 
Integral Tentu dan Aplikasinya,

* 
Barisan dan Deret (kekonvergenan barisan dan deret).


EMT (bersama Maxima) dapat digunakan untuk melakukan semua perhitungan
di dalam kalkulus, baik secara numerik maupun analitik (eksak).


## Mendefinisikan Fungsi

Terdapat beberapa cara mendefinisikan fungsi pada EMT, yakni:


* 
Menggunakan format nama_fungsi := rumus fungsi (untuk fungsi
* numerik),

* 
Menggunakan format nama_fungsi &amp;= rumus fungsi (untuk fungsi
* simbolik, namun dapat dihitung secara numerik),

* 
Menggunakan format nama_fungsi &amp;&amp;= rumus fungsi (untuk fungsi
* simbolik murni, tidak dapat dihitung langsung),

* 
Fungsi sebagai program EMT.


Setiap format harus diawali dengan perintah function (bukan sebagai
ekspresi).


Berikut adalah adalah beberapa contoh cara mendefinisikan fungsi:


$$f(x)=2x^2+e^{\sin(x)}.$$\>function f(x) := 2\*x^2+exp(sin(x)) // fungsi numerik

\>f(0), f(1), f(pi)


    1
    4.31977682472
    20.7392088022

\>f(a) // tidak dapat dihitung nilainya


    Variable or function a not found.
    Error in:
    f(a) // tidak dapat dihitung nilainya ...
       ^

Plot kurva fungsi di atas :


\>plot2d("f(x)",-5,5,-1,5):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-002.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-002.png)

Berikutnya kita definisikan fungsi:


$$g(x)=\frac{\sqrt{x^2-3x}}{x+1}.$$\>function g(x) := sqrt(x^2-3\*x)/(x+1)

\>g(3)


    0

\>g(0)


    0

\>g(1) // kompleks, tidak dapat dihitung oleh fungsi numerik


    Floating point error!
    Error in sqrt
    Try "trace errors" to inspect local variables after errors.
    g:
        useglobal; return sqrt(x^2-3*x)/(x+1) 
    Error in:
    g(1) // kompleks, tidak dapat dihitung oleh fungsi numerik ...
        ^

Plot kurva fungsi di atas :


\>plot2d("g(x)",-50,50,-50,50):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-004.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-004.png)

\>f(g(5)) // komposisi fungsi


    2.20920171961

\>g(f(5))


    0.950898070639

\>function h(x) := f(g(x)) // definisi komposisi fungsi 

\>h(5) // sama dengan f(g(5))


    2.20920171961

Silakan Anda plot kurva fungsi komposisi fungsi f dan g:


$$h(x)=f(g(x))$$dan


$$u(x)=g(f(x))$$bersama-sama kurva fungsi f dan g dalam satu bidang koordinat.


Plot kurva fungsi komposisi fungsi f dan g:


\>plot2d("f(x)",-10,10,-10,20); plot2d("g(x)",color=blue,\>add); ...  
\>   plot2d("h(x)",color=green,\>add);  ...  
\>   labelbox(["f(x)","g(x)","h(x)"],colors=[black,blue,green]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-007.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-007.png)

\>function u(x) := g(f(x)) 

\>plot2d("f(x)",-10,10,-10,20); plot2d("g(x)",color=blue,\>add); ...  
\>   plot2d("u(x)",color=green,\>add); ...  
\>   labelbox(["f(x)","g(x)","u(x)"],colors=[black,blue,green]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-008.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-008.png)

\>f(0:10) // nilai-nilai f(0), f(1), f(2), ..., f(10)


    [1,  4.31978,  10.4826,  19.1516,  32.4692,  50.3833,  72.7562,
    99.929,  130.69,  163.51,  200.58]

\>fmap(0:10) // sama dengan f(0:10), berlaku untuk semua fungsi


    [1,  4.31978,  10.4826,  19.1516,  32.4692,  50.3833,  72.7562,
    99.929,  130.69,  163.51,  200.58]

\>gmap(200:210)


    [0.987534,  0.987596,  0.987657,  0.987718,  0.987778,  0.987837,
    0.987896,  0.987954,  0.988012,  0.988069,  0.988126]

Misalkan kita akan mendefinisikan fungsi


$$f(x) = \begin{cases} x^3 & x>0 \\ x^2 & x\le 0. \end{cases}$$Fungsi tersebut tidak dapat didefinisikan sebagai fungsi numerik
secara "inline" menggunakan format :=, melainkan didefinisikan sebagai
program. Perhatikan, kata "map" digunakan agar fungsi dapat menerima
vektor sebagai input, dan hasilnya berupa vektor. Jika tanpa kata
"map" fungsinya hanya dapat menerima input satu nilai.


\>function map f(x) ...


      if x>0 then return x^3
      else return x^2
      endif;
    endfunction
</pre>
\>f(1)


    1

\>f(-2)


    4

\>f(-5:5)


    [25,  16,  9,  4,  1,  0,  1,  8,  27,  64,  125]

\>aspect(1.5); plot2d("f(x)",-5,5):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-010.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-010.png)

\>function f(x) &= 2\*E^x // fungsi simbolik


    
                                        x
                                     2 E
    

\>$f(a) // nilai fungsi secara simbolik


$$2\,e^{a}$$\>f(E) // nilai fungsi berupa bilangan desimal


    30.308524483

\>$f(E), $float(%)


$$30.30852448295852$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-013.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-013.png)

\>function g(x) &= 3\*x+1


    
                                   3 x + 1
    

\>function h(x) &= f(g(x)) // komposisi fungsi


    
                                     3 x + 1
                                  2 E
    

\>plot2d("h(x)",-1,1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-014.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-014.png)

# Latihan

Bukalah buku Kalkulus. Cari dan pilih beberapa (paling sedikit 5
fungsi berbeda tipe/bentuk/jenis) fungsi dari buku tersebut, kemudian
definisikan fungsi-fungsi tersebut dan komposisinya di EMT pada
baris-baris perintah berikut (jika perlu tambahkan lagi). Untuk setiap
fungsi, hitung beberapa nilainya, baik untuk satu nilai maupun vektor.
Gambar grafik fungsi-fungsi tersebut dan komposisi-komposisi 2 fungsi.


Juga, carilah fungsi beberapa (dua) variabel. Lakukan hal sama seperti
di atas.


\> function f(x) := x^2-1

\> f(1), f(0), f(-6)


    0
    -1
    35

\> f(-6:1)


    [35,  24,  15,  8,  3,  0,  -1,  0]

\> plot2d("f(x)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-015.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-015.png)

\> function g(x) := sin(x)+2

\> g(pi), g(pi/6), g(pi/3), g(0:pi)


    2
    2.5
    2.86602540378
    [2,  2.84147,  2.9093,  2.14112]

\> plot2d("g(x)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-016.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-016.png)

\> function h(x) := sqrt(2x+1)

\> h(2), h(6), h(0:5) 


    2.2360679775
    3.60555127546
    [1,  1.73205,  2.23607,  2.64575,  3,  3.31662]

\> plot2d("h(x)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-017.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-017.png)

\> function i(x) := log(2x)+1

\> i(1), i(10), i(1:10)


    1.69314718056
    3.99573227355
    [1.69315,  2.38629,  2.79176,  3.07944,  3.30259,  3.48491,  3.63906,
    3.77259,  3.89037,  3.99573]

\> plot2d("i(x)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-018.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-018.png)

\> function j(x) := abs(x+3)

\> j(-5), j(5), j(-5:5)


    2
    8
    [2,  1,  0,  1,  2,  3,  4,  5,  6,  7,  8]

\> plot2d("j(x)",-20,20):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-019.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-019.png)

\> function a(x) := g(f(x))

\> a(1), a(2), a(0:2)


    2
    2.14112000806
    [1.15853,  2,  2.14112]

\> plot2d("a(x)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-020.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-020.png)

\> function b(x) := h(i(x))

\> b(1), b(5), b(1:2)


    2.09434819481
    2.75774730278
    [2.09435,  2.40262]

\> plot2d("b(x)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-021.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-021.png)

\> function k(x,y) := x^2+y^2

\> k(1,1), k(3,1)


    2
    10

\> plot3d("k(x,y)"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-022.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-022.png)

# Menghitung Limit

Definisi Limit


Limit merupakan nilai hampiran suatu variabel pada suatu bilangan
real. Berikut adalah notasi limit:


$$\lim \limits_{x \to c} f(x)=L$$Notasi tersebut menyatakan bahwa f(x) untuk niai x mendekati c sama
dengan L. F(x) disini dapat berupa bermacam-macam jenis fungsi. Dan L
dapat berupa konstanta, ataupun "und" (tak terdefinisi), "ind" (tak
tentu namun terbatas), "infinity" (kompleks tak hingga). Begitupun
dengan batas c, dapat berupa sebarang nilai atau pada tak hingga
(-inf, minf, dan inf).


$$\mbox{Definisi}$$$$\mbox{(Pengertian limit secara intuisi). Untuk mengatakan bahwa}$$$$\lim \limits_{x \to c} f(x)=L \mbox{ berarti bilamana x dekat,}$$$$\mbox{ tetapi berlainan dengan c, maka f(x) dekat ke L.}$$Cara mencari limit fungsi:


1. Substitusi


2. Faktorisasi


3. Kali sekawan (merasionalkan bentuk akar)


Definisi Limit Sepihak (Limit Kiri-Kanan)


Sebuah fungsi dapat dikatakan memiliki limit apabila limit kanan dan
limit kiri nya memiliki nilai yang sama. Dimana, limit dari fungsi
tersebut adalah nilai dari limit kanan dan limit kiri fungsi yang
bernilai sama tadi.


$$\mbox{Definisi}$$$$\mbox{(limit-kiri dan limit-kanan). Untuk mengatakan bahwa}$$$$\lim \limits_{x \to c^+} f(x)=L \mbox{ berarti bahwa bilamana x dekat}$$$$\mbox{ tetapi pada sebelah kanan c, maka f(x) adalah dekat ke L.}$$$$\mbox{ Serupa, untuk mengatakan bahwa } \lim \limits_{x \to c^-} f(x)=L$$$$ \mbox{ berarti bahwa bilangan x dekat tetapi pada sebelah kiri c,}$$$$\mbox{ maka f(x) adalah dekat ke L.}$$Hubungan antara limit dengan limit sepihak(kiri/kanan):


$$\lim \limits_{x \to c} f(x)=L \iff \lim \limits_{x \to c^-} f(x)=L \mbox{ dan } \lim \limits_{x \to c^+} f(x)=L$$$$\mbox{Jika }\lim \limits_{x \to c^-} f(x) \ne \lim \limits_{x \to c^+} f(x) \mbox{ maka } \lim \limits_{x \to c} f(x) \mbox{ tidak ada.}$$Limit pada EMT


Perhitungan limit pada EMT dapat dilakukan dengan menggunakan fungsi
Maxima, yakni "limit". Fungsi "limit" dapat digunakan untuk menghitung
limit fungsi dalam bentuk ekspresi maupun fungsi yang sudah
didefinisikan sebelumnya. Nilai limit dapat dihitung pada sebarang
nilai atau pada tak hingga (-inf, minf, dan inf). Limit kiri dan limit
kanan juga dapat dihitung, dengan cara memberi opsi "plus" atau
"minus". Hasil limit dapat berupa nilai, "und" (tak definisi), "ind"
(tak tentu namun terbatas), "infinity" (kompleks tak hingga).


Perhatikan beberapa contoh berikut. Perhatikan cara menampilkan
perhitungan secara lengkap, tidak hanya menampilkan hasilnya saja.


\>$showev('limit(sqrt(x^2-3\*x)/(x+1),x,inf))


$$\lim_{x\rightarrow \infty }{\frac{\sqrt{x^2-3\,x}}{x+1}}=1$$\>$limit((x^3-13\*x^2+51\*x-63)/(x^3-4\*x^2-3\*x+18),x,3)


$$-\frac{4}{5}$$$$\lim_{x\rightarrow 3}{\frac{x^3-13\,x^2+51\,x-63}{x^3-4\,x^2-3\,x+  18}}=-\frac{4}{5}$$Fungsi tersebut diskontinu di titik x=3. Berikut adalah grafik
fungsinya.


\>aspect(1.5); plot2d("(x^3-13\*x^2+51\*x-63)/(x^3-4\*x^2-3\*x+18)",0,4); plot2d(3,-4/5,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-040.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-040.png)

\>$limit(2\*x\*sin(x)/(1-cos(x)),x,0)


$$4$$$$2\,\left(\lim_{x\rightarrow 0}{\frac{x\,\sin x}{1-\cos x}}\right)=4$$Fungsi tersebut diskontinu di titik x=0. Berikut adalah grafik
fungsinya.


\>plot2d("2\*x\*sin(x)/(1-cos(x))",-pi,pi); plot2d(0,4,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-043.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-043.png)

\>$limit(cot(7\*h)/cot(5\*h),h,0)


$$\frac{5}{7}$$$$\lim_{h\rightarrow 0}{\frac{\cot \left(7\,h\right)}{\cot \left(5\,h  \right)}}=\frac{5}{7}$$Fungsi tersebut juga diskontinu (karena tidak terdefinisi) di x=0.
Berikut adalah grafiknya.


\>plot2d("cot(7\*x)/cot(5\*x)",-0.001,0.001); plot2d(0,5/7,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-046.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-046.png)

\>$showev('limit(((x/8)^(1/3)-1)/(x-8),x,8))


$$\lim_{x\rightarrow 8}{\frac{\frac{x^{\frac{1}{3}}}{2}-1}{x-8}}=  \frac{1}{24}$$Fungsi tersebut diskontinu di x=8. Berikut adalah grafiknya.


\>plot2d("((x/8)^(1/3)-1)/(x-8)",-20,20); plot2d(8,1/24,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-048.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-048.png)

\>$showev('limit(1/(2\*x-1),x,0))


$$\lim_{x\rightarrow 0}{\frac{1}{2\,x-1}}=-1$$Fungsi tersebut diskontinu di x=0. Berikut adalah grafiknya.


\>plot2d("1/(2\*x-1)",-1,1,-6,6); plot2d(0,-1,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-050.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-050.png)

\>$showev('limit((x^2-3\*x-10)/(x-5),x,5))


$$\lim_{x\rightarrow 5}{\frac{x^2-3\,x-10}{x-5}}=7$$Fungsi tersebut diskontinu di x=5. Berikut adalah grafiknya.


\>plot2d("(x^2-3\*x-10)/(x-5)",-5,10); plot2d(5,7,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-052.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-052.png)

\>$showev('limit(sqrt(x^2+x)-x,x,inf))


$$\lim_{x\rightarrow \infty }{\sqrt{x^2+x}-x}=\frac{1}{2}$$Berikut adalah grafiknya.


\>plot2d("sqrt(x^2+x)-x"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-054.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-054.png)

\>$showev('limit(abs(x-1)/(x-1),x,1,minus))


$$\lim_{x\uparrow 1}{\frac{\left| x-1\right| }{x-1}}=-1$$Sedangkan limit untuk x menuju 1 dari kanan sebagai berikut.


\>$showev('limit(abs(x-1)/(x-1),x,1,plus))


$$\lim_{x\downarrow 1}{\frac{\left| x-1\right| }{x-1}}=1$$Fungsi tersebut diskontinu di x=1. Berikut adalah grafiknya.


\>plot2d("(abs(x-1))/(x-1)"); plot2d(1,1,\>points,style="ow",\>add);  ...  
\>   plot2d(1,-1,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-057.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-057.png)

\>$showev('limit(sin(x)/x,x,0))


$$\lim_{x\rightarrow 0}{\frac{\sin x}{x}}=1$$\>plot2d("sin(x)/x",-pi,pi); plot2d(0,1,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-059.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-059.png)

\>$showev('limit(sin(x^3)/x,x,0))


$$\lim_{x\rightarrow 0}{\frac{\sin x^3}{x}}=0$$Fungsi tersebut diskontinu di x=0. Berikut adalah grafiknya.


\>plot2d("(sin(x^3))/x",-pi,pi,-1,1); plot2d(0,0,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-061.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-061.png)

\>$showev('limit(log(x), x, minf))


$$\lim_{x\rightarrow  -\infty }{\log x}={\it infinity}$$\>$showev('limit((-2)^x,x, inf))


$$\lim_{x\rightarrow \infty }{\left(-2\right)^{x}}={\it infinity}$$\>$showev('limit(t-sqrt(2-t),t,2,minus))


$$\lim_{t\uparrow 2}{t-\sqrt{2-t}}=2$$\>$showev('limit(t-sqrt(2-t),t,2,plus))


$$\lim_{t\downarrow 2}{t-\sqrt{2-t}}=2$$\>$showev('limit(t-sqrt(2-t),t,5,plus)) // Perhatikan hasilnya


$$\lim_{t\downarrow 5}{t-\sqrt{2-t}}=5-\sqrt{3}\,i$$\>plot2d("x-sqrt(2-x)",0,2):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-067.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-067.png)

\>$showev('limit((x^2-9)/(2\*x^2-5\*x-3),x,3))


$$\lim_{x\rightarrow 3}{\frac{x^2-9}{2\,x^2-5\,x-3}}=\frac{6}{7}$$Fungsi tersebut diskontinu di x=3. Berikut adalah grafiknya.


\>plot2d("(x^2-9)/(2\*x^2-5\*x-3)",-10,10,-5,5); plot2d(3,6/7,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-069.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-069.png)

\>$showev('limit((1-cos(x))/x,x,0))


$$\lim_{x\rightarrow 0}{\frac{1-\cos x}{x}}=0$$Fungsi tersebut diskontinu di x=0. Berikut adalah grafiknya.


\>plot2d("(1-cos(x))/x",-4pi,4pi,-1,1); plot2d(0,0,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-071.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-071.png)

\>$showev('limit((x^2+abs(x))/(x^2-abs(x)),x,0))


$$\lim_{x\rightarrow 0}{\frac{\left| x\right| +x^2}{x^2-\left| x  \right| }}=-1$$Fungsi tersebut diskontinu di x=0. Berikut adalah grafiknya.


\>plot2d("(x^2+abs(x))/(x^2-abs(x))",-2,2,-20,20);  ...  
\>   plot2d(0,-1,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-073.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-073.png)

\>$showev('limit((1+1/x)^x,x,inf))


$$\lim_{x\rightarrow \infty }{\left(\frac{1}{x}+1\right)^{x}}=e$$\>plot2d("(1+1/x)^x",0,1000):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-075.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-075.png)

\>$showev('limit((1+k/x)^x,x,inf))


$$\lim_{x\rightarrow \infty }{\left(\frac{k}{x}+1\right)^{x}}=e^{k}$$\>$showev('limit((1+x)^(1/x),x,0))


$$\lim_{x\rightarrow 0}{\left(x+1\right)^{\frac{1}{x}}}=e$$Berikut adalah grafiknya.


\>plot2d("(1+x)^(1/x)",-5,20,-5,30):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-078.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-078.png)

\>$showev('limit((x/(x+k))^x,x,inf))


$$\lim_{x\rightarrow \infty }{\left(\frac{x}{x+k}\right)^{x}}=e^ {- k   }$$\>$showev('limit((E^x-E^2)/(x-2),x,2))


$$\lim_{x\rightarrow 2}{\frac{e^{x}-e^2}{x-2}}=e^2$$Fungsi tersebut diskontinu di x=0. Berikut adalah grafiknya.


\>plot2d("(E^x-E^2)/(x-2)",-5,20,-5,30); plot2d(2,E^2,\>points,style="ow",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-081.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-081.png)

\>$showev('limit(sin(1/x),x,0))


$$\lim_{x\rightarrow 0}{\sin \left(\frac{1}{x}\right)}={\it ind}$$\>$showev('limit(sin(1/x),x,inf))


$$\lim_{x\rightarrow \infty }{\sin \left(\frac{1}{x}\right)}=0$$\>plot2d("sin(1/x)",-0.001,0.001):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-084.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-084.png)

# Latihan

Bukalah buku Kalkulus. Cari dan pilih beberapa (paling sedikit 5
fungsi berbeda tipe/bentuk/jenis) fungsi dari buku tersebut, kemudian
definisikan di EMT pada baris-baris perintah berikut (jika perlu
tambahkan lagi). Untuk setiap fungsi, hitung nilai limit fungsi
tersebut di beberapa nilai dan di tak hingga. Gambar grafik fungsi
tersebut untuk mengkonfirmasi nilai-nilai limit tersebut.


\>function f(x) &= x^3+3


    
                                     3
                                    x  + 3
    

\>$showev('limit(f(x),x,0)), $showev('limit(f(x),x,1)), ...  
\>   $showev('limit(f(x),x,inf))


$$\lim_{x\rightarrow \infty }{x^3+3}=\infty $$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-086.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-086.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-087.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-087.png)

\>plot2d("f(x)",-3,3,-8,8):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-088.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-088.png)

\>function g(x) &= (2/x)+1


    
                                    2
                                    - + 1
                                    x
    

\>$showev('limit(g(x),x,1)), $showev('limit(g(x),x,3)), ...  
\>   $showev('limit(g(x),x,inf))


$$\lim_{x\rightarrow \infty }{\frac{2}{x}+1}=1$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-090.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-090.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-091.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-091.png)

\>plot2d("g(x)",-20,20,-20,20):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-092.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-092.png)

\>function h(x) &= (sqrt(9+x^2)/(x-3))


    
                                       2
                                 sqrt(x  + 9)
                                 ------------
                                    x - 3
    

\>$showev('limit(h(x),x,1)), $showev('limit(h(x),x,4)), ...  
\>   $showev('limit(h(x),x,inf))


$$\lim_{x\rightarrow \infty }{\frac{\sqrt{x^2+9}}{x-3}}=1$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-094.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-094.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-095.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-095.png)

\>plot2d("h(x)",-20,20,-20,20):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-096.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-096.png)

\>function i(x) &= (tan(x)/(2\*x))


    
                                    tan(x)
                                    ------
                                     2 x
    

\>$showev('limit(i(x),x,0)),  ...  
\>   $showev('limit(i(x),x,3)), ...  
\>   $showev('limit(i(x),x,inf))


$$\frac{\lim_{x\rightarrow \infty }{\frac{\tan x}{x}}}{2}=\frac{  \lim_{x\rightarrow \infty }{\frac{\tan x}{x}}}{2}$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-098.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-098.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-099.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-099.png)

\>plot2d("i(x)",-5,5,-5,5):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-100.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-100.png)

\>function j(x) &= (abs(x)-1)


    
                                 mabs(x) - 1
    

\>$showev('limit(j(x),x,-5)),  ...  
\>   $showev('limit(j(x),x,3)), ...  
\>   $showev('limit(j(x),x,inf))


$$\lim_{x\rightarrow \infty }{\left| x\right| -1}=\infty $$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-102.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-102.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-103.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-103.png)

\>plot2d("j(x)",-5,5,-5,5):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-104.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-104.png)

# Turunan Fungsi

Definisi turunan:


$$f'(x) = \lim_{h\to 0} \frac{f(x+h)-f(x)}{h}$$Berikut adalah contoh-contoh menentukan turunan fungsi dengan
menggunakan definisi turunan (limit).


\>$showev('limit(((x+h)^2-x^2)/h,h,0)) // turunan x^2


$$\lim_{h\rightarrow 0}{\frac{\left(x+h\right)^2-x^2}{h}}=2\,x$$\>p &= expand((x+h)^2-x^2)|simplify; $p //pembilang dijabarkan dan disederhanakan


$$2\,h\,x+h^2$$\>q &=ratsimp(p/h); $q // ekspresi yang akan dihitung limitnya disederhanakan


$$2\,x+h$$\>$limit(q,h,0) // nilai limit sebagai turunan


$$2\,x$$\>$showev('limit(((x+h)^n-x^n)/h,h,0)) // turunan x^n


$$\lim_{h\rightarrow 0}{\frac{\left(x+h\right)^{n}-x^{n}}{h}}=n\,x^{n  -1}$$Mengapa hasilnya seperti itu? Tuliskan atau tunjukkan bahwa hasil
limit tersebut benar, sehingga benar turunan fungsinya benar.  Tulis
penjelasan Anda di komentar ini.


Sebagai petunjuk, ekspansikan (x+h)^n dengan menggunakan teorema
binomial.


Jawaban :


$$f'(x) = \lim_{h\to 0} \frac{f(x+h)-f(x)}{h}$$

Untuk


$$f(x)=x^{n}$$$$\frac{d}{dx}sin(x) = \lim_{h\to 0} \frac{(x+h)^{n}-x^{n}}{h}$$

Dengan


$$(a+b)^{n}=\sum_{k=0}^n a^{k}b^{n-k}$$

maka


$$= \lim_{h\to 0} \frac{(x^{n}+\frac{n}{1!}x^{n-1}h+\frac{n(n-1)}{2!}x^{n-2}h^2+\frac{n(n-1)(n-2)}{3!}x^{n-3}h^{3}+...)-x^{n}}{h}$$$$= \lim_{h\to 0} \frac{n.x^{n-1}h+\frac{n(n-1)}{2!}x^{n-2}h^2+\frac{n(n-1)(n-2)}{3!}x^{n-3}h^{3}+...}{h}$$$$= \lim_{h\to 0} n.x^{n-1}+\frac{n(n-1)}{2!}.x^{n-2}h+\frac{n(n-1)(n-2)}{3!}.x^{n-3}h^{2}+...$$$$= n.x^{n-1}+0+0+...+0$$$$= n.x^{n-1}$$

Jadi, terbukti benar bahwa


$$f'(x^n) = n.x^{n-1}$$\>$showev('limit((sin(x+h)-sin(x))/h,h,0)) // turunan sin(x)


$$\lim_{h\rightarrow 0}{\frac{\sin \left(x+h\right)-\sin x}{h}}=\cos   x$$Mengapa hasilnya seperti itu? Tuliskan atau tunjukkan bahwa hasil
limit tersebut


benar, sehingga benar turunan fungsinya benar.  Tulis penjelasan Anda
di komentar ini.


Sebagai petunjuk, ekspansikan sin(x+h) dengan menggunakan rumus jumlah
dua sudut.


Jawaban :


$$f'(x) = \lim_{h\to 0} \frac{sin(x+h)-sin(x)}{h}$$$$sin(a+b)=sin(a)cos(a)+cos(a)sin(b)$$$$= \lim_{h\to 0} \frac{sin(x)cos(h)+cos(x)sin(h)-sin(x)}{h}$$$$= \lim_{h\to 0} sinx.\frac{cos(h)-1}{h}+\lim_{h\to 0} cos(x).\frac{sin(h)}{h}$$$$= sin(x).0+cos(x).1$$$$= cos(x)$$Jadi, terbukti benar bahwa


$$f'(sin(x)) = cos(x)$$\>$showev('limit((log(x+h)-log(x))/h,h,0)) // turunan log(x)


$$\lim_{h\rightarrow 0}{\frac{\log \left(x+h\right)-\log x}{h}}=  \frac{1}{x}$$Mengapa hasilnya seperti itu? Tuliskan atau tunjukkan bahwa hasil
limit tersebut


benar, sehingga benar turunan fungsinya benar.  Tulis penjelasan Anda
di komentar ini.


Sebagai petunjuk, gunakan sifat-sifat logaritma dan hasil limit pada
bagian sebelumnya di atas.


Jawaban :


$$f'(x) = \lim_{h\to 0} \frac{log(x+h)-log x}{h}$$$$=\lim_{h\to 0} \frac{\frac{d}{dh}(log(x+h)-log x)}{\frac{d}{dh}(h)}$$$$=\lim_{h\to 0} \frac{\frac{1}{x+h}}{1}$$$$=\lim_{h\to 0} \frac{1}{x+h}$$$$=\frac{1}{x}$$

Jadi, terbukti benar bahwa


$$f'(x) = \lim_{h\to 0} \frac{log(x+h)-log x}{h} = \frac{1}{x}$$\>$showev('limit((1/(x+h)-1/x)/h,h,0)) // turunan 1/x


$$\lim_{h\rightarrow 0}{\frac{\frac{1}{x+h}-\frac{1}{x}}{h}}=-\frac{1  }{x^2}$$\>$showev('limit((E^(x+h)-E^x)/h,h,0)) // turunan f(x)=e^x


    Answering "Is x an integer?" with "integer"
    Answering "Is x an integer?" with "integer"
    Answering "Is x an integer?" with "integer"
    Answering "Is x an integer?" with "integer"
    Answering "Is x an integer?" with "integer"
    Maxima is asking
    Acceptable answers are: yes, y, Y, no, n, N, unknown, uk
    Is x an integer?
    
    Use assume!
    Error in:
     $showev('limit((E^(x+h)-E^x)/h,h,0)) // turunan f(x)=e^x ...
                                         ^

Maxima bermasalah dengan limit:


$$\lim_{h\to 0}\frac{e^{x+h}-e^x}{h}.$$Oleh karena itu diperlukan trik khusus agar hasilnya benar.


\>$showev('limit((E^h-1)/h,h,0))


$$\lim_{h\rightarrow 0}{\frac{e^{h}-1}{h}}=1$$\>$showev('factor(E^(x+h)-E^x))


$${\it factor}\left(e^{x+h}-e^{x}\right)=\left(e^{h}-1\right)\,e^{x}$$\>$showev('limit(factor((E^(x+h)-E^x)/h),h,0)) // turunan f(x)=e^x


$$\left(\lim_{h\rightarrow 0}{\frac{e^{h}-1}{h}}\right)\,e^{x}=e^{x}$$\>function f(x) &= x^x


    
                                       x
                                      x
    

\>$showev('limit(f(x),x,0))


$$\lim_{x\rightarrow 0}{x^{x}}=1$$Silakan Anda gambar kurva


$$y=x^x.$$Berikut gambar kurvanya.


\>plot2d("x^x"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-143.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-143.png)

\>$showev('limit((f(x+h)-f(x))/h,h,0)) // turunan f(x)=x^x


$$\lim_{h\rightarrow 0}{\frac{\left(x+h\right)^{x+h}-x^{x}}{h}}=  {\it infinity}$$Di sini Maxima juga bermasalah terkait limit:


$$\lim_{h\to 0} \frac{(x+h)^{x+h}-x^x}{h}.$$Dalam hal ini diperlukan asumsi nilai x.


\>&assume(x\>0); $showev('limit((f(x+h)-f(x))/h,h,0)) // turunan f(x)=x^x


$$\lim_{h\rightarrow 0}{\frac{\left(x+h\right)^{x+h}-x^{x}}{h}}=x^{x}  \,\left(\log x+1\right)$$Mengapa hasilnya seperti itu? Tuliskan atau tunjukkan bahwa hasil
limit tersebut benar, sehingga benar turunan fungsinya benar. Tulis
penjelasan Anda di komentar ini.


Jawaban :


$$f'(x) = \lim_{h\to 0} \frac{(x+h)^{x+h}-x^x}{h}$$$$=\lim_{h\to 0} \frac{\frac{d}{dh}((x+h)^{x+h}-x^x)}{\frac{d}{dh}(h)}$$$$=\lim_{h\to 0} (x+h)^{x+h}(log(x+h)+1)$$$$= x^x(log(x)+1)$$Jadi, benar bahwa 


$$\lim_{h\to 0} \frac{(x+h)^{x+h}-x^x}{h} = x^x(log(x)+1)$$\>&forget(x\>0) // jangan lupa, lupakan asumsi untuk kembali ke semula


    
                                   [x &gt; 0]
    

\>&forget(x<0)


    
                                   [x &lt; 0]
    

\>&facts()


    
                                 [W5460 &gt; 0]
    

\>$showev('limit((asin(x+h)-asin(x))/h,h,0)) // turunan arcsin(x)


$$\lim_{h\rightarrow 0}{\frac{\arcsin \left(x+h\right)-\arcsin x}{h}}=  \frac{1}{\sqrt{1-x^2}}$$Mengapa hasilnya seperti itu? Tuliskan atau tunjukkan bahwa hasil
limit tersebut benar, sehingga benar turunan fungsinya benar. Tulis
penjelasan Anda di komentar ini.


Jawaban :


$$f'(x) = \lim_{h\to 0} \frac{arcsin(x+h)-arcsin(x)}{h}$$...


\>$showev('limit((tan(x+h)-tan(x))/h,h,0)) // turunan tan(x)


$$\lim_{h\rightarrow 0}{\frac{\tan \left(x+h\right)-\tan x}{h}}=  \frac{1}{\cos ^2x}$$Mengapa hasilnya seperti itu? Tuliskan atau tunjukkan bahwa hasil
limit tersebut benar, sehingga benar turunan fungsinya benar. Tulis
penjelasan Anda di komentar ini.


Jawaban :


$$f'(x) = \lim_{h\to 0} \frac{tan(x+h)-tan(x)}{h}$$$$= \lim_{h\to 0} \frac{\frac{sin(x+h)}{cos(x+h)}-\frac{sin(x)}{cos(x)}}{h}$$$$= \lim_{h\to 0} \frac{cos(x)sin(x+h)-cos(x+h)sin(x)}{hcos(x)cos(x+h)}$$$$= \frac{sec(x) (\lim_{h\to 0} \frac{cos(x)sin(x+h)-cos(x+h)sin(x)}{h})}{cos(x)}$$$$= \frac{sec(x) (\lim_{h\to 0} (cos(x)cos(x+h)+sin(x)sin(x+h)))}{cos(x)}$$$$= \frac{sec(x)}{cos(x)}$$$$= \frac{1}{cos^2(x)}$$Jadi, benar bahwa


$$\lim_{h\to 0} \frac{tan(x+h)-tan(x)}{h} = \frac{1}{cos^2(x)}$$\>function f(x) &= sinh(x) // definisikan f(x)=sinh(x)


    
                                   sinh(x)
    

\>function df(x) &= limit((f(x+h)-f(x))/h,h,0); $df(x) // df(x) = f'(x)


$$\frac{e^ {- x }\,\left(e^{2\,x}+1\right)}{2}$$Hasilnya adalah cosh(x), karena


$$\frac{e^x+e^{-x}}{2}=\cosh(x).$$\>plot2d(["f(x)","df(x)"],-pi,pi,color=[blue,red]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-165.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-165.png)

\>function f(x) &= sin(3\*x^5+7)^2


    
                                   2    5
                                sin (3 x  + 7)
    

\>diff(f,3), diffc(f,3)


    1198.32948904
    1198.72863721

Apakah perbedaan diff dan diffc?


Perbedaan diff dan diffc, yaitu :


function diff (f$, x, n, h) menghitung turunan ke-n (n&lt;6) dari f di
titik x. Diferensiasi numerik pada dasarnya agak tidak akurat


ungsi umum. Untuk mendapatkan perkiraan yang baik, yang pertama


turunan menggunakan 4 evaluasi fungsi.


function diffc (f$, x, h) menghitung turunan pertama untuk fungsi
analitik nyata dan diffc ini menghitung dengan lebih akurat untuk
fungsi, yang bersifat analitik dan nyata dihargai pada garis nyata.


\>$showev('diff(f(x),x))


$$\frac{d}{d\,x}\,\sin ^2\left(3\,x^5+7\right)=30\,x^4\,\cos \left(3  \,x^5+7\right)\,\sin \left(3\,x^5+7\right)$$\>$% with x=3


$${\it \%at}\left(\frac{d}{d\,x}\,\sin ^2\left(3\,x^5+7\right) , x=3  \right)=2430\,\cos 736\,\sin 736$$\>$float(%)


$${\it \%at}\left(\frac{d^{1.0}}{d\,x^{1.0}}\,\sin ^2\left(3.0\,x^5+  7.0\right) , x=3.0\right)=1198.728637211748$$\>plot2d(f,0,3.1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-169.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-169.png)

\>function f(x) &=5\*cos(2\*x)-2\*x\*sin(2\*x) // mendifinisikan fungsi f


    
                          5 cos(2 x) - 2 x sin(2 x)
    

\>function df(x) &=diff(f(x),x) // fd(x) = f'(x)


    
                         - 12 sin(2 x) - 4 x cos(2 x)
    

\>$'f(1)=f(1), $float(f(1)), $'f(2)=f(2), $float(f(2)) // nilai f(1) dan f(2)


$$-0.2410081230863468$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-171.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-171.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-172.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-172.png)

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-173.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-173.png)

\>xp=solve("df(x)",1,2,0) // solusi f'(x)=0 pada interval [1, 2]


    1.35822987384

\>df(xp), f(xp) // cek bahwa f'(xp)=0 dan nilai ekstrim di titik tersebut


    0
    -5.67530133759

\>plot2d(["f(x)","df(x)"],0,2\*pi,color=[blue,red]): //grafik fungsi dan turunannya


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-174.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-174.png)

Perhatikan titik-titik "puncak" grafik y=f(x) dan nilai turunan pada
saat grafik fungsinya mencapai titik "puncak" tersebut.


# Latihan

Bukalah buku Kalkulus. Cari dan pilih beberapa (paling sedikit 5
fungsi berbeda tipe/bentuk/jenis) fungsi dari buku tersebut, kemudian
definisikan di EMT pada baris-baris perintah berikut (jika perlu
tambahkan lagi). Untuk setiap fungsi, tentukan turunannya dengan
menggunakan definisi turunan (limit), menggunakan perintah diff, dan
secara manual (langkah demi langkah yang dihitung dengan Maxima)
seperti contoh-contoh di atas. Gambar grafik fungsi asli dan fungsi
turunannya pada sumbu koordinat yang sama.


Fungsi 1


\>function f(x) &= 2\*x^5+4


    
                                      5
                                   2 x  + 4
    

\>$showev('limit((f(x+h)-f(x))/h,h,0)) // dengan definisi turunan


$$\lim_{h\rightarrow 0}{\frac{2\,\left(x+h\right)^5-2\,x^5}{h}}=10\,x  ^4$$\>function df(x) &= diff(f(x),x) // dengan diff


    
                                        4
                                    10 x
    

\>a &= expand(2\*(x+h)^5-2\*x^5)|simplify; $a 


$$10\,h\,x^4+20\,h^2\,x^3+20\,h^3\,x^2+10\,h^4\,x+2\,h^5$$\>b &= ratsimp(a/h)


    
                     4         3       2  2       3        4
                 10 x  + 20 h x  + 20 h  x  + 10 h  x + 2 h
    

\>$limit(b,h,0) 


$$10\,x^4$$\>plot2d(["f(x)","df(x)"],-2,2,-6,10,color=[blue,red]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-178.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-178.png)

Fungsi 2


\>function f(x) &= sin(x)^2+cos(x)


    
                                  2
                               sin (x) + cos(x)
    

\>$showev('limit((f(x+h)-f(x))/h,h,0)) // dengan definisi turunan


$$\lim_{h\rightarrow 0}{\frac{\sin ^2\left(x+h\right)+\cos \left(x+h  \right)-\sin ^2x-\cos x}{h}}=\left(2\,\cos x-1\right)\,\sin x$$\>function df(x) &= diff(f(x),x) // dengan diff


    
                           2 cos(x) sin(x) - sin(x)
    

\>a &= expand(sin(x+h)^2+cos(x+h)-sin(x)^2-cos(x))|simplify; $a 


$$\sin ^2\left(x+h\right)+\cos \left(x+h\right)-\sin ^2x-\cos x$$\>b &= ratsimp(a/h)


    
                    2                          2
                 sin (x + h) + cos(x + h) - sin (x) - cos(x)
                 -------------------------------------------
                                      h
    

\>$limit(b,h,0) 


$$\left(2\,\cos x-1\right)\,\sin x$$\>plot2d(["f(x)","df(x)"],-6,6,-2,2,color=[blue,red]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-182.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-182.png)

Fungsi 3


\>function f(x) &= sqrt(5\*x+1)


    
                                sqrt(5 x + 1)
    

\>$showev('limit((f(x+h)-f(x))/h,h,0)) // dengan definisi turunan


$$\lim_{h\rightarrow 0}{\frac{\sqrt{5\,\left(x+h\right)+1}-\sqrt{5\,x  +1}}{h}}=\frac{5}{2\,\sqrt{5\,x+1}}$$\>function df(x) &= diff(f(x),x) // dengan diff 


    
                                      5
                               ---------------
                               2 sqrt(5 x + 1)
    

\>a &= expand(sqrt(5\*(x+h)+1)-sqrt(5\*x+1))|simplify; $a 


$$\sqrt{5\,x+5\,h+1}-\sqrt{5\,x+1}$$\>b &= ratsimp(a/h)


    
                     sqrt(5 x + 5 h + 1) - sqrt(5 x + 1)
                     -----------------------------------
                                      h
    

\>$limit(b,h,0) 


$$\frac{5}{2\,\sqrt{5\,x+1}}$$\>plot2d(["f(x)","df(x)"],-2,6,-2,6,color=[blue,red]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-186.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-186.png)

Fungsi 4


\>function f(x) &= (4\*x-7)^2\*(2\*x+3)


    
                                                2
                             (2 x + 3) (4 x - 7)
    

\>$showev('limit((f(x+h)-f(x))/h,h,0)) // dengan definisi turunan


$$\lim_{h\rightarrow 0}{\frac{\left(2\,\left(x+h\right)+3\right)\,  \left(4\,\left(x+h\right)-7\right)^2-\left(2\,x+3\right)\,\left(4\,x  -7\right)^2}{h}}=96\,x^2-128\,x-70$$\>&expand(f(x)); function df(x) &= diff(%,x) // dengan diff


    
                                  2
                              96 x  - 128 x - 70
    

\>a &= expand((2\*(x+h)+3)\*(4\*(x+h)-7)^2-(2\*x+3)\*(4\*x-7)^2)|simplify; $a 


$$96\,h\,x^2+96\,h^2\,x-128\,h\,x+32\,h^3-64\,h^2-70\,h$$\>b &= ratsimp(a/h)


    
                      2                        2
                  96 x  + (96 h - 128) x + 32 h  - 64 h - 70
    

\>$limit(b,h,0) 


$$96\,x^2-128\,x-70$$\>plot2d(["f(x)","df(x)"],color=[blue,red]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-190.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-190.png)

Fungsi 5


\>function f(x) &= sin(pi\*x)^2


    
                                     2
                                  sin (pi x)
    

\>$showev('limit((f(x+h)-f(x))/h,h,0)) // dengan definisi turunan


$$\lim_{h\rightarrow 0}{\frac{\sin ^2\left(\pi\,\left(x+h\right)  \right)-\sin ^2\left(\pi\,x\right)}{h}}=2\,\pi\,\cos \left(\pi\,x  \right)\,\sin \left(\pi\,x\right)$$\>function df(x) &= diff(f(x),x) // dengan diff


    
                           2 pi cos(pi x) sin(pi x)
    

\>a &= expand(sin(pi\*(x+h))^2-sin(pi\*x)^2)|simplify; $a 


$$\sin ^2\left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x\right)$$\>b &= ratsimp(a/h)


    
                           2                   2
                        sin (pi x + pi h) - sin (pi x)
                        ------------------------------
                                      h
    

\>$limit(b,h,0) 


$$2\,\pi\,\cos \left(\pi\,x\right)\,\sin \left(\pi\,x\right)$$\>plot2d(["f(x)","df(x)"],color=[blue,red]):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-194.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-194.png)

# Integral

EMT dapat digunakan untuk menghitung integral, baik integral tak tentu
maupun integral tentu. Untuk integral tak tentu (simbolik) sudah tentu
EMT menggunakan Maxima, sedangkan untuk perhitungan integral tentu EMT
sudah menyediakan beberapa fungsi yang mengimplementasikan algoritma
kuadratur (perhitungan integral tentu menggunakan metode numerik).


Pada notebook ini akan ditunjukkan perhitungan integral tentu dengan
menggunakan Teorema Dasar Kalkulus:


$$\int_a^b f(x)\ dx = F(b)-F(a), \quad \text{ dengan  } F'(x) = f(x).$$Fungsi untuk menentukan integral adalah integrate. Fungsi ini dapat
digunakan untuk menentukan, baik integral tentu maupun tak tentu (jika
fungsinya memiliki antiderivatif). Untuk perhitungan integral tentu
fungsi integrate menggunakan metode numerik (kecuali fungsinya tidak
integrabel, kita tidak akan menggunakan metode ini).


\>$showev('integrate(x^n,x))


    Answering "Is n equal to -1?" with "no"

$$\int {x^{n}}{\;dx}=\frac{x^{n+1}}{n+1}$$\>$showev('integrate(1/(1+x),x))


$$\int {\frac{1}{x+1}}{\;dx}=\log \left(x+1\right)$$\>$showev('integrate(1/(1+x^2),x))


$$\int {\frac{1}{x^2+1}}{\;dx}=\arctan x$$\>$showev('integrate(1/sqrt(1-x^2),x))


$$\int {\frac{1}{\sqrt{1-x^2}}}{\;dx}=\arcsin x$$\>$showev('integrate(sin(x),x,0,pi))


$$\int_{0}^{\pi}{\sin x\;dx}=2$$\>plot2d("sin(x)",0,2\*pi):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-201.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-201.png)

\>$showev('integrate(sin(x),x,a,b))


$$\int_{\sin ^2\left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x\right)  }^{\frac{\sin ^2\left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x  \right)}{h}}{\sin x\;dx}=\cos \left(\sin ^2\left(\pi\,x+\pi\,h  \right)-\sin ^2\left(\pi\,x\right)\right)-\cos \left(\frac{\sin ^2  \left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x\right)}{h}\right)$$\>$showev('integrate(x^n,x,a,b))


    Answering "Is n positive, negative or zero?" with "positive"

$$\int_{\sin ^2\left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x\right)  }^{\frac{\sin ^2\left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x  \right)}{h}}{x^{n}\;dx}=\frac{\left(\sin ^2\left(\pi\,x+\pi\,h  \right)-\sin ^2\left(\pi\,x\right)\right)\,\left(\frac{\sin ^2\left(  \pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x\right)}{h}\right)^{n}}{h\,n  +h}-\frac{\left(\sin ^2\left(\pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,  x\right)\right)^{n+1}}{n+1}$$\>$showev('integrate(x^2\*sqrt(2\*x+1),x))


$$\int {x^2\,\sqrt{2\,x+1}}{\;dx}=\frac{\left(2\,x+1\right)^{\frac{7  }{2}}}{28}-\frac{\left(2\,x+1\right)^{\frac{5}{2}}}{10}+\frac{\left(  2\,x+1\right)^{\frac{3}{2}}}{12}$$\>$showev('integrate(x^2\*sqrt(2\*x+1),x,0,2))


$$\int_{0}^{2}{x^2\,\sqrt{2\,x+1}\;dx}=\frac{2\,5^{\frac{5}{2}}}{21}-  \frac{2}{105}$$\>$ratsimp(%)


$$\int_{0}^{2}{x^2\,\sqrt{2\,x+1}\;dx}=\frac{2\,5^{\frac{7}{2}}-2}{  105}$$\>$showev('integrate((sin(sqrt(x)+a)\*E^sqrt(x))/sqrt(x),x,0,pi^2))


$$\int_{0}^{\pi^2}{\frac{e^{\sqrt{x}}\,\sin \left(\sin ^2\left(\pi\,x  +\pi\,h\right)-\sin ^2\left(\pi\,x\right)+\sqrt{x}\right)}{\sqrt{x}}  \;dx}=\int_{0}^{\pi^2}{\frac{e^{\sqrt{x}}\,\sin \left(\sin ^2\left(  \pi\,x+\pi\,h\right)-\sin ^2\left(\pi\,x\right)+\sqrt{x}\right)}{  \sqrt{x}}\;dx}$$\>$factor(%)


$$\int_{0}^{\pi^2}{\frac{e^{\sqrt{x}}\,\sin \left(\sin ^2\left(\pi\,  \left(x+h\right)\right)-\sin ^2\left(\pi\,x\right)+\sqrt{x}\right)}{  \sqrt{x}}\;dx}=\int_{0}^{\pi^2}{\frac{e^{\sqrt{x}}\,\sin \left(\sin   ^2\left(\pi\,\left(x+h\right)\right)-\sin ^2\left(\pi\,x\right)+  \sqrt{x}\right)}{\sqrt{x}}\;dx}$$\>function map f(x) &= E^(-x^2)


    
                                        2
                                     - x
                                    E
    

\>$showev('integrate(f(x),x))


$$\int {e^ {- x^2 }}{\;dx}=\frac{\sqrt{\pi}\,\mathrm{erf}\left(x  \right)}{2}$$Fungsi f tidak memiliki antiturunan, integralnya masih memuat integral
lain.


$$erf(x) = \int \frac{e^{-x^2}}{\sqrt{\pi}} \ dx.$$Kita tidak dapat menggunakan teorema Dasar kalkulus untuk menghitung
integral tentu fungsi tersebut jika semua batasnya berhingga. Dalam
hal ini dapat digunakan metode numerik (rumus kuadratur).


Misalkan kita akan menghitung:


$$\int_{0}^{\pi}{e^ {- x^2 }\;dx}$$\>x=0:0.1:pi-0.1; plot2d(x,f(x+0.1),\>bar); plot2d("f(x)",0,pi,\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-212.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-212.png)

Integral tentu


$$\int_{0}^{\pi}{e^ {- x^2 }\;dx}$$dapat dihampiri dengan jumlah luas persegi-persegi panjang di bawah
kurva y=f(x) tersebut. Langkah-langkahnya adalah sebagai berikut.


\>t &= makelist(a,a,0,pi-0.1,0.1); // t sebagai list untuk menyimpan nilai-nilai x

\>fx &= makelist(f(t[i]+0.1),i,1,length(t)); // simpan nilai-nilai f(x)

\>// jangan menggunakan x sebagai list, kecuali Anda pakar Maxima!


Hasilnya adalah:


$$\int_{0}^{\pi}{e^ {- x^2 }\;dx}=0.8362196102528469$$Jumlah tersebut diperoleh dari hasil kali lebar sub-subinterval (=0.1)
dan jumlah nilai-nilai f(x) untuk x = 0.1, 0.2, 0.3, ..., 3.2.


\>0.1\*sum(f(x+0.1)) // cek langsung dengan perhitungan numerik EMT


    0.836219610253

Untuk mendapatkan nilai integral tentu yang mendekati nilai
sebenarnya, lebar sub-intervalnya dapat diperkecil lagi, sehingga
daerah di bawah kurva tertutup semuanya, misalnya dapat digunakan
lebar subinterval 0.001. (Silakan dicoba!)


Meskipun Maxima tidak dapat menghitung integral tentu fungsi tersebut
untuk batas-batas yang berhingga, namun integral tersebut dapat
dihitung secara eksak jika batas-batasnya tak hingga. Ini adalah salah
satu keajaiban di dalam matematika, yang terbatas tidak dapat dihitung
secara eksak, namun yang tak hingga malah dapat dihitung secara eksak.


\>$showev('integrate(f(x),x,0,inf))


$$\int_{0}^{\infty }{e^ {- x^2 }\;dx}=\frac{\sqrt{\pi}}{2}$$Tunjukkan kebenaran hasil di atas!


Berikut adalah contoh lain fungsi yang tidak memiliki antiderivatif,
sehingga integral tentunya hanya dapat dihitung dengan metode numerik.


\>function f(x) &= x^x


    
                                       x
                                      x
    

\>$showev('integrate(f(x),x,0,1))


$$\int_{0}^{1}{x^{x}\;dx}=\int_{0}^{1}{x^{x}\;dx}$$\>x=0:0.1:1-0.01; plot2d(x,f(x+0.01),\>bar); plot2d("f(x)",0,1,\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-217.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-217.png)

Maxima gagal menghitung integral tentu tersebut secara langsung
menggunakan perintah integrate. Berikut kita lakukan seperti contoh
sebelumnya untuk mendapat hasil atau pendekatan nilai integral tentu
tersebut.


\>t &= makelist(a,a,0,1-0.01,0.01);

\>fx &= makelist(f(t[i]+0.01),i,1,length(t));


$$\int_{0}^{1}{x^{x}\;dx}=0.7834935879025506$$Apakah hasil tersebut cukup baik? perhatikan gambarnya.


\>function f(x) &= sin(3\*x^5+7)^2


    
                                   2    5
                                sin (3 x  + 7)
    

\>integrate(f,0,1)


    0.542581176074

\>&showev('integrate(f(x),x,0,1))


    
             1                           1              pi
            /                      gamma(-) sin(14) sin(--)
            [     2    5                 5              10
            I  sin (3 x  + 7) dx = ------------------------
            ]                                  1/5
            /                              10 6
             0
           4/5                  1          4/5                  1
     - (((6    gamma_incomplete(-, 6 I) + 6    gamma_incomplete(-, - 6 I))
                                5                               5
                 4/5                    1
     sin(14) + (6    I gamma_incomplete(-, 6 I)
                                        5
        4/5                    1                       pi
     - 6    I gamma_incomplete(-, - 6 I)) cos(14)) sin(--) - 60)/120
                               5                       10
    

\>&float(%)


    
             1.0
            /
            [       2      5
            I    sin (3.0 x  + 7.0) dx = 
            ]
            /
             0.0
    0.09820784258795788 - 0.008333333333333333
     (0.3090169943749474 (0.1367372182078336
     (4.192962712629476 I gamma__incomplete(0.2, 6.0 I)
     - 4.192962712629476 I gamma__incomplete(0.2, - 6.0 I))
     + 0.9906073556948704 (4.192962712629476 gamma__incomplete(0.2, 6.0 I)
     + 4.192962712629476 gamma__incomplete(0.2, - 6.0 I))) - 60.0)
    

\>$showev('integrate(x\*exp(-x),x,0,1)) // Integral tentu (eksak)


$$\int_{0}^{1}{x\,e^ {- x }\;dx}=1-2\,e^ {- 1 }$$# Aplikasi Integral Tentu

\>plot2d("x^3-x",-0.1,1.1); plot2d("-x^2",\>add);  ...  
\>   b=solve("x^3-x+x^2",0.5); x=linspace(0,b,200); xi=flipx(x); ...  
\>   plot2d(x|xi,x^3-x|-xi^2,\>filled,style="|",fillcolor=1,\>add): // Plot daerah antara 2 kurva


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-220.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-220.png)

\>a=solve("x^3-x+x^2",0), b=solve("x^3-x+x^2",1) // absis titik-titik potong kedua kurva


    0
    0.61803398875

\>integrate("(-x^2)-(x^3-x)",a,b) // luas daerah yang diarsir


    0.0758191713542

Hasil tersebut akan kita bandingkan dengan perhitungan secara analitik.


\>a &= solve((-x^2)-(x^3-x),x); $a // menentukan absis titik potong kedua kurva secara eksak


$$\left[ x=\frac{-\sqrt{5}-1}{2} , x=\frac{\sqrt{5}-1}{2} , x=0   \right] $$\>$showev('integrate(-x^2-x^3+x,x,0,(sqrt(5)-1)/2)) // Nilai integral secara eksak


$$\int_{0}^{\frac{\sqrt{5}-1}{2}}{-x^3-x^2+x\;dx}=\frac{13-5^{\frac{3  }{2}}}{24}$$\>$float(%)


$$\int_{0.0}^{0.6180339887498949}{-1.0\,x^3-1.0\,x^2+x\;dx}=  0.07581917135421037$$## Panjang Kurva

Hitunglah panjang kurva berikut ini dan luas daerah di dalam kurva
tersebut.


$$\gamma(t) = (r(t) \cos(t), r(t) \sin(t))$$dengan


$$r(t) = 1 + \dfrac{\sin(3t)}{2},\quad 0\le t\le 2\pi.$$\>t=linspace(0,2pi,1000); r=1+sin(3\*t)/2; x=r\*cos(t); y=r\*sin(t); ...  
\>   plot2d(x,y,\>filled,fillcolor=red,style="/",r=1.5): // Kita gambar kurvanya terlebih dahulu


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-226.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-226.png)

\>function r(t) &= 1+sin(3\*t)/2; $'r(t)=r(t)


$$r\left(t\right)=\frac{\sin \left(3\,t\right)}{2}+1$$\>function fx(t) &= r(t)\*cos(t); $'fx(t)=fx(t)


$${\it fx}\left(t\right)=\cos t\,\left(\frac{\sin \left(3\,t\right)}{  2}+1\right)$$\>function fy(t) &= r(t)\*sin(t); $'fy(t)=fy(t)


$${\it fy}\left(t\right)=\sin t\,\left(\frac{\sin \left(3\,t\right)}{  2}+1\right)$$\>function ds(t) &= trigreduce(radcan(sqrt(diff(fx(t),t)^2+diff(fy(t),t)^2))); $'ds(t)=ds(t)


$${\it ds}\left(t\right)=\sqrt{a^2+1}\,e^{a\,t}$$\>$integrate(ds(x),x,0,2\*pi) //panjang (keliling) kurva


$$\sqrt{a^2+1}\,\left(\frac{e^{2\,\pi\,a}}{a}-\frac{1}{a}\right)$$Maxima gagal melakukan perhitungan eksak integral tersebut.


Berikut kita hitung integralnya secara umerik dengan perintah EMT.


\>integrate("ds(x)",0,2\*pi)


    8.78817491636

Spiral Logaritmik


$$x=e^{ax}\cos x,\ y=e^{ax}\sin x.$$\>a=0.1; plot2d("exp(a\*x)\*cos(x)","exp(a\*x)\*sin(x)",r=2,xmin=0,xmax=2\*pi):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-233.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-233.png)

\>&kill(a) // hapus expresi a


    
                                     done
    

\>function fx(t) &= exp(a\*t)\*cos(t); $'fx(t)=fx(t)


$${\it fx}\left(t\right)=e^{a\,t}\,\cos t$$\>function fy(t) &= exp(a\*t)\*sin(t); $'fy(t)=fy(t)


$${\it fy}\left(t\right)=e^{a\,t}\,\sin t$$\>function df(t) &= trigreduce(radcan(sqrt(diff(fx(t),t)^2+diff(fy(t),t)^2))); $'df(t)=df(t)


$${\it df}\left(t\right)=\sqrt{a^2+1}\,e^{a\,t}$$\>S &=integrate(df(t),t,0,2\*%pi); $S // panjang kurva (spiral)


$$\sqrt{a^2+1}\,\left(\frac{e^{2\,\pi\,a}}{a}-\frac{1}{a}\right)$$\>S(a=0.1) // Panjang kurva untuk a=0.1


    8.78817491636

Soal:


Tunjukkan bahwa keliling lingkaran dengan jari-jari r adalah K=2.pi.r.


Jawaban :


\>$showev('integrate(sqrt(r^2\*sin(x)^2+r^2\*cos(x)^2),x,0,2\*pi))


$$\int_{0}^{2\,\pi}{\sqrt{r^2\,\sin ^2x+r^2\,\cos ^2x}\;dx}=2\,\pi\,  \left| r\right| $$Berikut adalah contoh menghitung panjang parabola.


\>plot2d("x^2",xmin=-1,xmax=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-239.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-239.png)

\>$showev('integrate(sqrt(1+diff(x^2,x)^2),x,-1,1))


$$\int_{-1}^{1}{\sqrt{4\,x^2+1}\;dx}=\frac{{\rm asinh}\; 2+2\,\sqrt{5  }}{2}$$\>$float(%)


$$\int_{-1.0}^{1.0}{\sqrt{4.0\,x^2+1.0}\;dx}=2.957885715089195$$\>x=-1:0.2:1; y=x^2; plot2d(x,y);  ...  
\>     plot2d(x,y,points=1,style="o#",add=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-242.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-242.png)

Panjang tersebut dapat dihampiri dengan menggunakan jumlah panjang
ruas-ruas garis yang menghubungkan titik-titik pada parabola tersebut.


\>i=1:cols(x)-1; sum(sqrt((x[i+1]-x[i])^2+(y[i+1]-y[i])^2))


    2.95191957027

Hasilnya mendekati panjang yang dihitung secara eksak. Untuk
mendapatkan hampiran yang cukup akurat, jarak antar titik dapat
diperkecil, misalnya 0.1, 0.05, 0.01, dan seterusnya. Cobalah Anda
ulangi perhitungannya dengan nilai-nilai tersebut.


\>x=-1:0.1:1; y=x^2; plot2d(x,y);  ...  
\>     plot2d(x,y,points=1,style="o#",add=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-243.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-243.png)

\>i=1:cols(x)-1; sum(sqrt((x[i+1]-x[i])^2+(y[i+1]-y[i])^2))


    2.95639479497

\>x=-1:0.05:1; y=x^2; plot2d(x,y);  ...  
\>   plot2d(x,y,points=1,style="o#",add=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-244.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-244.png)

\>i=1:cols(x)-1; sum(sqrt((x[i+1]-x[i])^2+(y[i+1]-y[i])^2))


    2.95751302406

\>x=-1:0.01:1; y=x^2; plot2d(x,y);  ...  
\>   plot2d(x,y,points=1,style="o#",add=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-245.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-245.png)

\>i=1:cols(x)-1; sum(sqrt((x[i+1]-x[i])^2+(y[i+1]-y[i])^2))


    2.95787080795

## Koordinat Kartesius

Berikut diberikan contoh perhitungan panjang kurva menggunakan
koordinat Kartesius. Kita akan hitung panjang kurva dengan persamaan
implisit:


$$x^3+y^3-3xy=0.$$\>z &= x^3+y^3-3\*x\*y; $z


$$y^3-3\,x\,y+x^3$$\>plot2d(z,r=2,level=0,n=100):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-248.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-248.png)

Kita tertarik pada kurva di kuadran pertama.


\>plot2d(z,a=0,b=2,c=0,d=2,level=[-10;0],n=100,contourwidth=3,style="/"):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-249.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-249.png)

Kita selesaikan persamaannya untuk x.


\>$z with y=l\*x, sol &= solve(%,x); $sol


$$\left[ x=\frac{3\,l}{l^3+1} , x=0 \right] $$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-251.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-251.png)

Kita gunakan solusi tersebut untuk mendefinisikan fungsi dengan Maxima.


\>function f(l) &= rhs(sol[1]); $'f(l)=f(l)


$$f\left(l\right)=\frac{3\,l}{l^3+1}$$Fungsi tersebut juga dapat digunaka untuk menggambar kurvanya. Ingat,
bahwa fungsi tersebut adalah nilai x dan nilai y=l*x, yakni x=f(l) dan
y=l*f(l).


\>plot2d(&f(x),&x\*f(x),xmin=-0.5,xmax=2,a=0,b=2,c=0,d=2,r=1.5):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-253.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-253.png)

Elemen panjang kurva adalah:


$$ds=\sqrt{f'(l)^2+(lf'(l)+f(l))^2}.$$\>function ds(l) &= ratsimp(sqrt(diff(f(l),l)^2+diff(l\*f(l),l)^2)); $'ds(l)=ds(l)


$${\it ds}\left(l\right)=\frac{\sqrt{9\,l^8+36\,l^6-36\,l^5-36\,l^3+  36\,l^2+9}}{\sqrt{l^{12}+4\,l^9+6\,l^6+4\,l^3+1}}$$\>$integrate(ds(l),l,0,1)


$$\int_{0}^{1}{\frac{\sqrt{9\,l^8+36\,l^6-36\,l^5-36\,l^3+36\,l^2+9}  }{\sqrt{l^{12}+4\,l^9+6\,l^6+4\,l^3+1}}\;dl}$$Integral tersebut tidak dapat dihitung secara eksak menggunakan
Maxima. Kita hitung integral etrsebut secara numerik dengan Euler.
Karena kurva simetris, kita hitung untuk nilai variabel integrasi dari
0 sampai 1, kemudian hasilnya dikalikan 2.


\>2\*integrate("ds(x)",0,1)


    4.91748872168

\>2\*romberg(&ds(x),0,1)// perintah Euler lain untuk menghitung nilai hampiran integral yang sama


    4.91748872168

Perhitungan di datas dapat dilakukan untuk sebarang fungsi x dan y
dengan mendefinisikan fungsi EMT, misalnya kita beri nama
panjangkurva. Fungsi ini selalu memanggil Maxima untuk menurunkan
fungsi yang diberikan.


\>function panjangkurva(fx,fy,a,b) ...


    ds=mxm("sqrt(diff(@fx,x)^2+diff(@fy,x)^2)");
    return romberg(ds,a,b);
    endfunction
</pre>
\>panjangkurva("x","x^2",-1,1) // cek untuk menghitung panjang kurva parabola sebelumnya


    2.95788571509

Bandingkan dengan nilai eksak di atas.


\>2\*panjangkurva(mxm("f(x)"),mxm("x\*f(x)"),0,1) // cek contoh terakhir, bandingkan hasilnya!


    4.91748872168

Kita hitung panjang spiral Archimides berikut ini dengan fungsi tersebut.


\>plot2d("x\*cos(x)","x\*sin(x)",xmin=0,xmax=2\*pi,square=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-257.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-257.png)

\>panjangkurva("x\*cos(x)","x\*sin(x)",0,2\*pi)


    21.2562941482

Berikut kita definisikan fungsi yang sama namun dengan Maxima, untuk
perhitungan eksak.


\>&kill(ds,x,fx,fy)


    
                                     done
    

\>function ds(fx,fy) &&= sqrt(diff(fx,x)^2+diff(fy,x)^2)


    
                               2              2
                      sqrt(diff (fy, x) + diff (fx, x))
    

\>sol &= ds(x\*cos(x),x\*sin(x)); $sol // Kita gunakan untuk menghitung panjang kurva terakhir di atas


$$\sqrt{\left(\cos x-x\,\sin x\right)^2+\left(\sin x+x\,\cos x\right)  ^2}$$\>$sol | trigreduce | expand, $integrate(%,x,0,2\*pi), %()


$$\frac{{\rm asinh}\; \left(2\,\pi\right)+2\,\pi\,\sqrt{4\,\pi^2+1}}{  2}$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-260.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-260.png)

    21.2562941482

Hasilnya sama dengan perhitungan menggunakan fungsi EMT.


Berikut adalah contoh lain penggunaan fungsi Maxima tersebut.


\>plot2d("3\*x^2-1","3\*x^3-1",xmin=-1/sqrt(3),xmax=1/sqrt(3),square=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-261.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-261.png)

\>sol &= radcan(ds(3\*x^2-1,3\*x^3-1)); $sol


$$3\,x\,\sqrt{9\,x^2+4}$$\>$showev('integrate(sol,x,0,1/sqrt(3))), $2\*float(%) // panjang kurva di atas


$$6.0\,\int_{0.0}^{0.5773502691896258}{x\,\sqrt{9.0\,x^2+4.0}\;dx}=  2.337835372767141$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-264.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-264.png)

## Sikloid

Berikut kita akan menghitung panjang kurva lintasan (sikloid) suatu
titik pada lingkaran yang berputar ke kanan pada permukaan datar.
Misalkan jari-jari lingkaran tersebut adalah r. Posisi titik pusat
lingkaran pada saat t adalah:


$$(rt,r).$$Misalkan posisi titik pada lingkaran tersebut mula-mula (0,0) dan
posisinya pada saat t adalah:


$$(r(t-\sin(t)),r(1-\cos(t))).$$Berikut kita plot lintasan tersebut dan beberapa posisi lingkaran
ketika t=0, t=pi/2, t=r*pi.


\>x &= r\*(t-sin(t))


    
                                r (t - sin(t))
    

\>y &= r\*(1-cos(t))


    
                                r (1 - cos(t))
    

Berikut kita gambar sikloid untuk r=1.


\>ex &= x-sin(x); ey &= 1-cos(x); aspect(1);

\>plot2d(ex,ey,xmin=0,xmax=4pi,square=1); ...  
\>     plot2d("2+cos(x)","1+sin(x)",xmin=0,xmax=2pi,\>add,color=blue); ...  
\>     plot2d([2,ex(2)],[1,ey(2)],color=red,\>add); ...  
\>     plot2d(ex(2),ey(2),\>points,\>add,color=red); ...  
\>     plot2d("2pi+cos(x)","1+sin(x)",xmin=0,xmax=2pi,\>add,color=blue); ...  
\>     plot2d([2pi,ex(2pi)],[1,ey(2pi)],color=red,\>add);  ...  
\>     plot2d(ex(2pi),ey(2pi),\>points,\>add,color=red):


    Variable or function t not found.
    Error in expression: r*(t-sin(t))-sin(r*(t-sin(t)))
    adaptiveeval:
        sx=f$(t;args());
    Try "trace errors" to inspect local variables after errors.
    plot2d:
        dw/n,dw/n^2,dw/n;args());

Berikut dihitung panjang lintasan untuk 1 putaran penuh. (Jangan salah
menduga bahwa panjang lintasan 1 putaran penuh sama dengan keliling
lingkaran!)


\>ds &= radcan(sqrt(diff(ex,x)^2+diff(ey,x)^2)); $ds=trigsimp(ds) // elemen panjang kurva sikloid


    Maxima said:
    diff: second argument must be a variable; found r*(t-sin(t))
     -- an error. To debug this try: debugmode(true);
    
    Error in:
    ds &amp;= radcan(sqrt(diff(ex,x)^2+diff(ey,x)^2)); $ds=trigsimp(ds ...
                                                 ^

\>ds &= trigsimp(ds); $ds


$${\it ds}$$\>$showev('integrate(ds,x,0,2\*pi)) // hitung panjang sikloid satu putaran penuh


    Maxima said:
    defint: variable of integration must be a simple or subscripted variable.
    defint: found r*(t-sin(t))
    #0: showev(f='integrate(ds,r*(t-sin(t)),0,2*pi))
     -- an error. To debug this try: debugmode(true);
    
    Error in:
     $showev('integrate(ds,x,0,2*pi)) // hitung panjang sikloid sat ...
                                     ^

\>integrate(mxm("ds"),0,2\*pi) // hitung secara numerik


    Illegal function result in map.
     %evalexpression:
        if maps then return %mapexpression1(x,f$;args());
    gauss:
        if maps then y=%evalexpression(f$,a+h-(h*xn)',maps;args());
    adaptivegauss:
        t1=gauss(f$,c,c+h;args(),=maps);
    Try "trace errors" to inspect local variables after errors.
    integrate:
        return adaptivegauss(f$,a,b,eps*1000;args(),=maps);

\>romberg(mxm("ds"),0,2\*pi) // cara lain hitung secara numerik


    Wrong argument!
    
    Cannot combine a symbolic expression here.
    Did you want to create a symbolic expression?
    Then start with &amp;.
    
    Try "trace errors" to inspect local variables after errors.
    romberg:
        if cols(y)==1 then return y*(b-a); endif;
    Error in:
    romberg(mxm("ds"),0,2*pi) // cara lain hitung secara numerik ...
                             ^

Perhatikan, seperti terlihat pada gambar, panjang sikloid lebih besar
daripada keliling lingkarannya, yakni:


$$2\pi.$$## Kurvatur (Kelengkungan) Kurva

image: Osculating.png


Aslinya, kelengkungan kurva diferensiabel (yakni, kurva mulus yang
tidak lancip) di titik P didefinisikan melalui lingkaran oskulasi
(yaitu, lingkaran yang melalui titik P dan terbaik memperkirakan,
paling banyak menyinggung kurva di sekitar P). Pusat dan radius
kelengkungan kurva di P adalah pusat dan radius lingkaran oskulasi.
Kelengkungan adalah kebalikan dari radius kelengkungan:


$$\kappa =\frac {1}{R}$$dengan R adalah radius kelengkungan. (Setiap lingkaran memiliki
kelengkungan ini pada setiap titiknya, dapat diartikan, setiap
lingkaran berputar 2pi sejauh 2piR.)


Definisi ini sulit dimanipulasi dan dinyatakan ke dalam rumus untuk
kurva umum. Oleh karena itu digunakan definisi lain yang ekivalen.


## Definisi Kurvatur dengan Fungsi Parametrik Panjang Kurva



Setiap kurva diferensiabel dapat dinyatakan dengan persamaan
parametrik terhadap panjang kurva s:


$$\gamma(s) = (x(s),\ y(s)),$$dengan x dan y adalah fungsi riil yang diferensiabel, yang memenuhi:


$$\|\gamma'(s)\|=\sqrt{x'(s)^2+y'(s)^2}=1.$$Ini berarti bahwa vektor singgung


$$\mathbf{T}(s)=(x'(s),\ y'(s))$$memiliki norm 1 dan merupakan vektor singgung satuan.


Apabila kurvanya memiliki turunan kedua, artinya turunan kedua x dan y
ada, maka T'(s) ada. Vektor ini merupakan normal kurva yang arahnya
menuju pusat kurvatur, norm-nya merupakan nilai kurvatur
(kelengkungan):


$$ \begin{aligned}\mathbf{T}(s) &= \mathbf{\gamma}'(s),\\ \mathbf{T}^{2}(s) &=1\ \text{(konstanta)}\Rightarrow \mathbf{T}'(s)\cdot \mathbf{T}(s)=0\\ \kappa(s) &=\|\mathbf {T}'(s)\|= \|\mathbf{\gamma}''(s)\|=\sqrt{x''(s)^{2}+y''(s)^{2}}.\end{aligned}$$Nilai


$$R(s)=\frac{1}{\kappa(s)}$$disebut jari-jari (radius) kelengkungan kurva.


Bilangan riil


$$ k(s) = \pm\kappa(s)$$disebut nilai kelengkungan bertanda.


Contoh:


Akan ditentukan kurvatur lingkaran


$$x=r\cos t,\ y= r\sin t.$$\>fx &= r\*cos(t); fy &=r\*sin(t);

\>&assume(t\>0,r\>0); s &=integrate(sqrt(diff(fx,t)^2+diff(fy,t)^2),t,0,t); s // elemen panjang kurva, panjang busur lingkaran (s)


    
                                     r t
    

\>&kill(s); fx &= r\*cos(s/r); fy &=r\*sin(s/r); // definisi ulang persamaan parametrik terhadap s dengan substitusi t=s/r

\>k &= trigsimp(sqrt(diff(fx,s,2)^2+diff(fy,s,2)^2)); $k // nilai kurvatur lingkaran dengan menggunakan definisi di atas


$$\frac{1}{r}$$Untuk representasi parametrik umum, misalkan


$$x = x(t),\ y= y(t)$$merupakan persamaan parametrik untuk kurva bidang yang
terdiferensialkan dua kali. Kurvatur untuk kurva tersebut
didefinisikan sebagai


$$\begin{aligned}\kappa &= \frac{d\phi}{ds}=\frac{\frac{d\phi}{dt}}{\frac{ds}{dt}}\quad (\phi \text{ adalah sudut kemiringan garis singgung dan }s \text{ adalah panjang kurva})\\ &=\frac{\frac{d\phi}{dt}}{\sqrt{(\frac{dx}{dt})^2+(\frac{dy}{dt})^2}}= \frac{\frac{d\phi}{dt}}{\sqrt{x'(t)^2+y'(t)^2}}.\end{aligned}.$$Selanjutnya, pembilang pada persamaan di atas dapat dicari sebagai
berikut.


$$\begin{aligned}\sec^2\phi\frac{d\phi}{dt} &= \frac{d}{dt}\left(\tan\phi\right)= \frac{d}{dt}\left(\frac{dy}{dx}\right)= \frac{d}{dt}\left(\frac{dy/dt}{dx/dt}\right)= \frac{d}{dt}\left(\frac{y'(t)}{x'(t)}\right)=\frac{x'(t)y''(t)-x''(t)y'(t)}{x'(t)^2}.\\ & \\ \frac{d\phi}{dt} &= \frac{1}{\sec^2\phi}\frac{x'(t)y''(t)-x''(t)y'(t)}{x'(t)^2}\\ &= \frac{1}{1+\tan^2\phi}\frac{x'(t)y''(t)-x''(t)y'(t)}{x'(t)^2}\\ &= \frac{1}{1+\left(\frac{y'(t)}{x'(t)}\right)^2}\frac{x'(t)y''(t)-x''(t)y'(t)}{x'(t)^2}\\ &= \frac{x'(t)y''(t)-x''(t)y'(t)}{x'(t)^2+y'(t)^2}.\end{aligned}$$Jadi, rumus kurvatur untuk kurva parametrik


$$x=x(t),\ y=y(t)$$adalah


$$\kappa(t) = \frac{x'(t)y''(t)-x''(t)y'(t)}{\left(x'(t)^2+y'(t)^2\right)^{3/2}}.$$Jika kurvanya dinyatakan dengan persamaan parametrik pada koordinat
kutub


$$x=r(\theta)\cos\theta,\ y=r(\theta)\sin\theta,$$maka rumus kurvaturnya adalah


$$\kappa(\theta) = \frac{r(\theta)^2+2r'(\theta)^2-r(\theta)r''(\theta)}{\left(r'(\theta)^2+r'(\theta)^2\right)^{3/2}}.$$(Silakan Anda turunkan rumus tersebut!)


Contoh:


Lingkaran dengan pusat (0,0) dan jari-jari r dapat dinyatakan dengan
persamaan parametrik


$$x=r\cos t,\ y=r\sin t.$$Nilai kelengkungan lingkaran tersebut adalah


$$\kappa(t)=\frac{x'(t)y''(t)-x''(t)y'(t)}{\left(x'(t)^2+y'(t)^2\right)^{3/2}}=\frac{r^2}{r^3}=\frac 1 r.$$Hasil cocok dengan definisi kurvatur suatu kelengkungan.


Kurva


$$y=f(x)$$dapat dinyatakan ke dalam persamaan parametrik


$$x=t,\ y=f(t),\ \text{ dengan } x'(t)=1,\ x''(t)=0,$$sehingga kurvaturnya adalah


$$\kappa(t) = \frac{y''(t)}{\left(1+y'(t)^2\right)^{3/2}}.$$Contoh:


Akan ditentukan kurvatur parabola


$$y=ax^2+bx+c.$$\>function f(x) &= a\*x^2+b\*x+c; $y=f(x)


$$y=a\,x^2+b\,x+c$$\>function k(x) &= (diff(f(x),x,2))/(1+diff(f(x),x)^2)^(3/2); $'k(x)=k(x) // kelengkungan parabola 


$$k\left(x\right)=\frac{2\,a}{\left(\left(2\,a\,x+b\right)^2+1\right)  ^{\frac{3}{2}}}$$\>function f(x) &= x^2+x+1; $y=f(x) // akan kita plot kelengkungan parabola untuk a=b=c=1


$$y=x^2+x+1$$\>function k(x) &= (diff(f(x),x,2))/(1+diff(f(x),x)^2)^(3/2); $'k(x)=k(x) // kelengkungan parabola 


$$k\left(x\right)=\frac{2}{\left(\left(2\,x+1\right)^2+1\right)^{  \frac{3}{2}}}$$Berikut kita gambar parabola tersebut beserta kurva kelengkungan,
kurva jari-jari kelengkungan dan salah satu lingkaran oskulasi di
titik puncak parabola. Perhatikan, puncak parabola dan jari-jari
lingkaran oskulasi di puncak parabola adalah


$$(-1/2,3/4),\ 1/k(2)=1/2,$$sehingga pusat lingkaran oskulasi adalah (-1/2, 5/4).


\>plot2d(["f(x)", "k(x)"],-2,1, color=[blue,red]); plot2d("1/k(x)",-1.5,1,color=green,\>add); ...  
\>   plot2d("-1/2+1/k(-1/2)\*cos(x)","5/4+1/k(-1/2)\*sin(x)",xmin=0,xmax=2pi,\>add,color=blue):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-296.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-296.png)

Untuk kurva yang dinyatakan dengan fungsi implisit


$$F(x,y)=0$$dengan turunan-turunan parsial


$$F_x=\frac{\partial F}{\partial x},\ F_y=\frac{\partial F}{\partial y},\ F_{xy}=\frac{\partial}{\partial y}\left(\frac{\partial F}{\partial x}\right),\ F_{xx}=\frac{\partial}{\partial x}\left(\frac{\partial F}{\partial x}\right),\ F_{yy}=\frac{\partial}{\partial y}\left(\frac{\partial F}{\partial y}\right),$$berlaku


$$F_x dx+ F_y dy = 0\text{ atau } \frac{dy}{dx}=-\frac{F_x}{F_y},$$sehingga kurvaturnya adalah


$$\kappa =\frac {F_y^2F_{xx}-2F_xF_yF_{xy}+F_x^2F_{yy}}{\left(F_x^2+F_y^2\right)^{3/2}}.$$(Silakan Anda turunkan sendiri!)


Contoh 1:


Parabola


$$y=ax^2+bx+c$$dapat dinyatakan ke dalam persamaan implisit


$$ax^2+bx+c-y=0.$$\>function F(x,y) &=a\*x^2+b\*x+c-y; $F(x,y)


$$-y+a\,x^2+b\,x+c$$\>Fx &= diff(F(x,y),x), Fxx &=diff(F(x,y),x,2), Fy &=diff(F(x,y),y), Fxy &=diff(diff(F(x,y),x),y), Fyy &=diff(F(x,y),y,2)  


    
                                  2 a x + b
    
    
                                     2 a
    
    
                                     - 1
    
    
                                      0
    
    
                                      0
    

\>function k(x) &= (Fy^2\*Fxx-2\*Fx\*Fy\*Fxy+Fx^2\*Fyy)/(Fx^2+Fy^2)^(3/2); $'k(x)=k(x) // kurvatur parabola tersebut


$$k\left(x\right)=\frac{2\,a}{\left(\left(2\,a\,x+b\right)^2+1\right)  ^{\frac{3}{2}}}$$Hasilnya sama dengan sebelumnya yang menggunakan persamaan parabola biasa.


# Latihan

* 
Bukalah buku Kalkulus.

* 
Cari dan pilih beberapa (paling sedikit 5 fungsi berbeda
* tipe/bentuk/jenis) fungsi dari buku tersebut, kemudian definisikan di
* EMT pada baris-baris perintah berikut (jika perlu tambahkan lagi).

* 
Untuk setiap fungsi, tentukan anti turunannya (jika ada), hitunglah
* integral tentu dengan batas-batas yang menarik (Anda tentukan
* sendiri), seperti contoh-contoh tersebut.

* 
Lakukan hal yang sama untuk fungsi-fungsi yang tidak dapat
* diintegralkan (cari sedikitnya 3 fungsi).

* 
Gambar grafik fungsi dan daerah integrasinya pada sumbu koordinat
* yang sama.

* 
Gunakan integral tentu untuk mencari luas daerah yang dibatasi oleh
* dua kurva yang berpotongan di dua titik. (Cari dan gambar kedua kurva
* dan arsir (warnai) daerah yang dibatasi oleh keduanya.)

* 
Gunakan integral tentu untuk menghitung volume benda putar kurva y=
* f(x) yang diputar mengelilingi sumbu x dari x=a sampai x=b, yakni


$$V = \int_a^b \pi (f(x)^2\ dx.$$(Pilih fungsinya dan gambar kurva dan benda putar yang dihasilkan.
Anda dapat mencari contoh-contoh bagaimana cara menggambar benda hasil
perputaran suatu kurva.)


- Gunakan integral tentu untuk menghitung panjang kurva y=f(x) dari
x=a sampai x=b dengan menggunakan rumus:


$$S = \int_a^b \sqrt{1+(f'(x))^2} \ dx.$$(Pilih fungsi dan gambar kurvanya.)


- Apabila fungsi dinyatakan dalam koordinat kutub x=f(r,t), y=g(r,t),
r=h(t), x=a bersesuaian dengan t=t0 dan x=b bersesuian dengan t=t1,
maka rumus di atas akan menjadi:


$$S=\int_{t_0}^{t_1} \sqrt{x'(t)^2+y'(t)^2}\ dt.$$* 
Pilih beberapa kurva menarik (selain lingkaran dan parabola) dari
* buku  kalkulus. Nyatakan setiap kurva tersebut dalam bentuk:
*   a. koordinat Kartesius (persamaan y=f(x))
*   b. koordinat kutub ( r=r(theta))
*   c. persamaan parametrik x=x(t), y=y(t)
*   d. persamaan implit F(x,y)=0

* 
Tentukan kurvatur masing-masing kurva dengan menggunakan keempat
* representasi tersebut (hasilnya harus sama).

* 
Gambarlah kurva asli, kurva kurvatur, kurva jari-jari lingkaran
* oskulasi, dan salah satu lingkaran oskulasinya.


Fungsi 1


\>function f(x) &= (4\*x-4)/3


    
                                   4 x - 4
                                   -------
                                      3
    

\>$showev('integrate(f(x),x)) 


$$\frac{\int {4\,x-4}{\;dx}}{3}=\frac{2\,x^2-4\,x}{3}$$\>$showev('integrate(f(x),x,0,5))


$$\frac{\int_{0}^{5}{4\,x-4\;dx}}{3}=10$$\>plot2d("f(x)",-2,4); plot2d("(2\*x^2-4\*x)/3",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-310.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-310.png)

Fungsi 2


\>function g(x) &= x^3+sqrt(x)


    
                                  3
                                 x  + sqrt(x)
    

\>$showev('integrate(g(x),x))


$$\int {x^3+\sqrt{x}}{\;dx}=\frac{x^4}{4}+\frac{2\,x^{\frac{3}{2}}}{3  }$$\>$showev('integrate(g(x),x,0,2))


$$\int_{0}^{2}{x^3+\sqrt{x}\;dx}=\frac{2^{\frac{5}{2}}+12}{3}$$\>plot2d("g(x)",0,5); plot2d("(x^4/4)+(2\*x^(3/2)/3)",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-313.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-313.png)

Fungsi 3


\>function h(x) &= sin(x)^4\*cos(x)


    
                                          4
                                cos(x) sin (x)
    

\>$showev('integrate(h(x),x))


$$\int {\cos x\,\sin ^4x}{\;dx}=\frac{\sin ^5x}{5}$$\>$showev('integrate(h(x),x,0,pi/2))


$$\int_{0}^{\frac{\pi}{2}}{\cos x\,\sin ^4x\;dx}=\frac{1}{5}$$\>plot2d("h(x)",0,5); plot2d("(sin(x)^5)/5",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-316.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-316.png)

Fungsi 4


\>function i(x) &= x\*sin(pi\*x^2)


    
                                           2
                                 x sin(pi x )
    

\>$showev('integrate(i(x),x))


$$\int {x\,\sin \left(\pi\,x^2\right)}{\;dx}=-\frac{\cos \left(\pi\,x  ^2\right)}{2\,\pi}$$\>$showev('integrate(i(x),x,0,1))


$$\int_{0}^{1}{x\,\sin \left(\pi\,x^2\right)\;dx}=\frac{1}{\pi}$$\>plot2d("i(x)"); plot2d("-((cos(pi\*x^2))/2\*pi)",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-319.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-319.png)

Fungsi 5


\>function j(x) &= (x)^(1/3)


    
                                      1/3
                                     x
    

\>$showev('integrate(j(x),x))


$$\int {x^{\frac{1}{3}}}{\;dx}=\frac{3\,x^{\frac{4}{3}}}{4}$$\>$showev('integrate(j(x),x,-1,8))


$$\int_{-1}^{8}{x^{\frac{1}{3}}\;dx}=\frac{45}{4}$$\>plot2d("j(x)"); plot2d("(3\*x^(4/3))/4",\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-322.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-322.png)

Akan digunakan integral tentu untuk mencari luas daerah yang dibatasi
oleh dua kurva yang berpotongan di dua titik. (Cari dan gambar kedua
kurva dan arsir (warnai) daerah yang dibatasi oleh keduanya.)


kurva 1 :


$$j(x)=x^{1/3}$$

kurva 2 :


$$J(x)=\frac{3x^{4/3}}{4}$$\>plot2d("j(x)"); plot2d("(3\*x^(4/3))/4",\>add); ...  
\>   b=solve("(x)^(1/3)-(3\*x^(4/3))/4",1); x=linspace(0,b,200); xi=flipx(x);  ...  
\>   plot2d(x|xi,(x)^(1/3)|(3\*xi^(4/3))/4,\>filled,style="|",fillcolor=1,\>add):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-325.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-325.png)

\>b=solve("(x)^(1/3)-(3\*x^(4/3))/4",1)


    1.33333333333

\>integrate("(x)^(1/3)-(3\*x^(4/3))/4",0,b)


    0.471703892699

\>a&=solve(((x)^(1/3)-(3\*x^(4/3))/4),x); $a


$$\left[ x=\frac{4}{3} , x=0 \right] $$\>$showev('integrate(((x)^(1/3)-3\*x^(4/3)/4),x,0,(4/3))), $float(%)


$$\int_{0.0}^{1.333333333333333}{x^{\frac{1}{3}}-0.75\,x^{\frac{4}{3}  }\;dx}=0.4717038926992323$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-328.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-328.png)

Gunakan integral tentu untuk menghitung volume benda putar kurva y=
f(x) yang diputar mengelilingi sumbu x dari x=a sampai x=b, yakni


$$V = \int_a^b \pi (f(x)^2\ dx.$$(Pilih fungsinya dan gambar kurva dan benda putar yang dihasilkan.
Anda dapat mencari contoh-contoh bagaimana cara menggambar benda hasil
perputaran suatu kurva.)


Jawaban :


\>function f(x) &= sqrt(x)


    
                                   sqrt(x)
    

\>$showev('integrate((pi\*(f(x))^2),x,0,4)), $float(%)


$$3.141592653589793\,\int_{0.0}^{4.0}{x\;dx}=25.13274122871834$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-331.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-331.png)

Gunakan integral tentu untuk menghitung panjang kurva y=f(x) dari x=a
sampai x=b dengan menggunakan rumus:


$$S = \int_a^b \sqrt{1+(f'(x))^2} \ dx.$$(Pilih fungsi dan gambar kurvanya.)


Jawaban :


\> function f(x) &= x^(3/2)


    
                                      3/2
                                     x
    

\>$showev('integrate((sqrt(1+diff(f(x),x)^2)),x,1,4)), $float(%)


$$\int_{1.0}^{4.0}{\sqrt{2.25\,x+1.0}\;dx}=7.633705416016242$$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-334.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-334.png)

\>plot2d("f(x)",1,4); plot2d(1,1,points=1,style="o#",add=1); ...  
\>   plot2d(4,8,points=1,style="o#",add=1):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-335.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-335.png)

# Barisan dan Deret

(Catatan: bagian ini belum lengkap. Anda dapat membaca contoh-contoh
pengguanaan EMT dan Maxima untuk menghitung limit barisan, rumus
jumlah parsial suatu deret, jumlah tak hingga suatu deret konvergen,
dan sebagainya. Anda dapat mengeksplor contoh-contoh di EMT atau
perbagai panduan penggunaan Maxima di software Maxima atau dari
Internet.)


Barisan dapat didefinisikan dengan beberapa cara di dalam EMT, di
antaranya:


* 
dengan cara yang sama seperti mendefinisikan vektor dengan
* elemen-elemen beraturan (menggunakan titik dua ":");

* 
menggunakan perintah "sequence" dan rumus barisan (suku ke -n);

* 
menggunakan perintah "iterate" atau "niterate";

* 
menggunakan fungsi Maxima "create_list" atau "makelist" untuk
* menghasilkan barisan simbolik;

* 
menggunakan fungsi biasa yang inputnya vektor atau barisan;

* 
menggunakan fungsi rekursif.


EMT menyediakan beberapa perintah (fungsi) terkait barisan, yakni:


* 
sum: menghitung jumlah semua elemen suatu barisan

* 
cumsum: jumlah kumulatif suatu barisan

* 
differences: selisih antar elemen-elemen berturutan


EMT juga dapat digunakan untuk menghitung jumlah deret berhingga
maupun deret tak hingga, dengan menggunakan perintah (fungsi) "sum".
Perhitungan dapat dilakukan secara numerik maupun simbolik dan eksak.


Berikut adalah beberapa contoh perhitungan barisan dan deret
menggunakan EMT.


\>1:10 // barisan sederhana


    [1,  2,  3,  4,  5,  6,  7,  8,  9,  10]

\>1:2:30


    [1,  3,  5,  7,  9,  11,  13,  15,  17,  19,  21,  23,  25,  27,  29]

# Iterasi dan Barisan

EMT menyediakan fungsi iterate("g(x)", x0, n) untuk melakukan iterasi


$$x_{k+1}=g(x_k), \ x_0=x_0, k= 1, 2, 3, ..., n.$$Berikut ini disajikan contoh-contoh penggunaan iterasi dan rekursi
dengan EMT. Contoh pertama menunjukkan pertumbuhan dari nilai awal
1000 dengan laju pertambahan 5%, selama 10 periode.


\>q=1.05; iterate("x\*q",1000,n=10)'


             1000 
             1050 
           1102.5 
          1157.63 
          1215.51 
          1276.28 
           1340.1 
           1407.1 
          1477.46 
          1551.33 
          1628.89 

Contoh berikutnya memperlihatkan bahaya menabung di bank pada masa
sekarang! Dengan bunga tabungan sebesar 6% per tahun atau 0.5% per
bulan dipotong pajak 20%, dan biaya administrasi 10000 per bulan,
tabungan sebesar 1 juta tanpa diambil selama sekitar 10 tahunan akan
habis diambil oleh bank!


\>r=0.005; plot2d(iterate("(1+0.8\*r)\*x-10000",1000000,n=130)):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-337.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-337.png)

Silakan Anda coba-coba, dengan tabungan minimal berapa agar tidak akan
habis diambil oleh bank dengan ketentuan bunga dan biaya administrasi
seperti di atas.


Berikut adalah perhitungan minimal tabungan agar aman di bank dengan
bunga sebesar r dan biaya administrasi a, pajak bunga 20%.


\>$solve(0.8\*r\*A-a,A), $% with [r=0.005, a=10] 


$$\left[ A=2500.0 \right] $$![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-339.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-339.png)

Berikut didefinisikan fungsi untuk menghitung saldo tabungan, kemudian
dilakukan iterasi.


\>function saldo(x,r,a) := round((1+0.8\*r)\*x-a,2);

\>iterate({{"saldo",0.005,10}},1000,n=6)


    [1000,  994,  987.98,  981.93,  975.86,  969.76,  963.64]

\>iterate({{"saldo",0.005,10}},2000,n=6)


    [2000,  1998,  1995.99,  1993.97,  1991.95,  1989.92,  1987.88]

\>iterate({{"saldo",0.005,10}},2500,n=6)


    [2500,  2500,  2500,  2500,  2500,  2500,  2500]

Tabungan senilai 2,5 juta akan aman dan tidak akan berubah nilai (jika
tidak ada penarikan), sedangkan jika tabungan awal kurang dari 2,5
juta, lama kelamaan akan berkurang meskipun tidak pernah dilakukan
penarikan uang tabungan.


\>iterate({{"saldo",0.005,10}},3000,n=6)


    [3000,  3002,  3004.01,  3006.03,  3008.05,  3010.08,  3012.12]

Tabungan yang lebih dari 2,5 juta baru akan bertambah jika tidak ada
penarikan.


Untuk barisan yang lebih kompleks dapat digunakan fungsi "sequence()".
Fungsi ini menghitung nilai-nilai x[n] dari semua nilai sebelumnya,
x[1],...,x[n-1] yang diketahui.


Berikut adalah contoh barisan Fibonacci.


$$x_n = x_{n-1}+x_{n-2}, \quad x_1=1, \quad x_2 =1$$\>sequence("x[n-1]+x[n-2]",[1,1],15)


    [1,  1,  2,  3,  5,  8,  13,  21,  34,  55,  89,  144,  233,  377,  610]

Barisan Fibonacci memiliki banyak sifat menarik, salah satunya adalah
akar pangkat ke-n suku ke-n akan konvergen ke pecahan emas:


\>$'(1+sqrt(5))/2=float((1+sqrt(5))/2)


$$\frac{\sqrt{5}+1}{2}=1.618033988749895$$\>plot2d(sequence("x[n-1]+x[n-2]",[1,1],250)^(1/(1:250))):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-342.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-342.png)

Barisan yang sama juga dapat dihasilkan dengan menggunakan loop.


\>x=ones(500); for k=3 to 500; x[k]=x[k-1]+x[k-2]; end;


Rekursi dapat dilakukan dengan menggunakan rumus yang tergantung pada
semua elemen sebelumnya. Pada contoh berikut, elemen ke-n merupakan
jumlah (n-1) elemen sebelumnya, dimulai dengan 1 (elemen ke-1). Jelas,
nilai elemen ke-n adalah 2^(n-2), untuk n=2, 4, 5, ....


\>sequence("sum(x)",1,10)


    [1,  1,  2,  4,  8,  16,  32,  64,  128,  256]

Selain menggunakan ekspresi dalam x dan n, kita juga dapat menggunakan
fungsi.


Pada contoh berikut, digunakan iterasi


$$x_n =A \cdot x_{n-1},$$dengan A suatu matriks 2x2, dan setiap x[n] merupakan matriks/vektor
2x1.


\>A=[1,1;1,2]; function suku(x,n) := A.x[,n-1]

\>sequence("suku",[1;1],6)


    Real 2 x 6 matrix
    
                1             2             5            13     ...
                1             3             8            21     ...

Hasil yang sama juga dapat diperoleh dengan menggunakan fungsi
perpangkatan matriks "matrixpower()". Cara ini lebih cepat, karena
hanya menggunakan perkalian matriks sebanyak log_2(n).


$$x_n=A.x_{n-1}=A^2.x_{n-2}=A^3.x_{n-3}= ... = A^{n-1}.x_1.$$\>sequence("matrixpower(A,n).[1;1]",1,6)


    Real 2 x 6 matrix
    
                1             5            13            34     ...
                1             8            21            55     ...

# Spiral Theodorus

image: Spiral_of_Theodorus.png


Spiral Theodorus (spiral segitiga siku-siku) dapat digambar secara
rekursif. Rumus rekursifnya adalah:


$$x_n = \left( 1 + \frac{i}{\sqrt{n-1}} \right) \, x_{n-1}, \quad x_1=1,$$yang menghasilkan barisan bilangan kompleks.


\>function g(n) := 1+I/sqrt(n)


Rekursinya dapat dijalankan sebanyak 17 untuk menghasilkan barisan 17
bilangan kompleks, kemudian digambar bilangan-bilangan kompleksnya.


\>x=sequence("g(n-1)\*x[n-1]",1,17); plot2d(x,r=3.5); textbox(latex("Spiral\\ Theodorus"),0.4):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-346.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-346.png)

Selanjutnya dihubungan titik 0 dengan titik-titik kompleks tersebut
menggunakan loop.


\>for i=1:cols(x); plot2d([0,x[i]],\>add); end:


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-347.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-347.png)

\> 


Spiral tersebut juga dapat didefinisikan menggunakan fungsi rekursif,
yang tidak memmerlukan indeks dan bilangan kompleks. Dalam hal ini
diigunakan vektor kolom pada bidang.


\>function gstep (v) ...


    w=[-v[2];v[1]];
    return v+w/norm(w);
    endfunction
</pre>
Jika dilakukan iterasi 16 kali dimulai dari [1;0] akan didapatkan
matriks yang memuat vektor-vektor dari setiap iterasi.


\>x=iterate("gstep",[1;0],16); plot2d(x[1],x[2],r=3.5,\>points):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-348.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-348.png)

# Kekonvergenan

Terkadang kita ingin melakukan iterasi sampai konvergen. Apabila
iterasinya tidak konvergen setelah ditunggu lama, Anda dapat
menghentikannya dengan menekan tombol [ESC].


\>iterate("cos(x)",1) // iterasi x(n+1)=cos(x(n)), dengan x(0)=1.


    0.739085133216

Iterasi tersebut konvergen ke penyelesaian persamaan


$$x = \cos(x).$$Iterasi ini juga dapat dilakukan pada interval, hasilnya adalah
barisan interval yang memuat akar tersebut.


\>hasil := iterate("cos(x)",~1,2~) //iterasi x(n+1)=cos(x(n)), dengan interval awal (1, 2)


    ~0.739085133211,0.7390851332133~

Jika interval hasil tersebut sedikit diperlebar, akan terlihat bahwa
interval tersebut memuat akar persamaan x=cos(x).


\>h=expand(hasil,100), cos(h) << h


    ~0.73908513309,0.73908513333~
    1

Iterasi juga dapat digunakan pada fungsi yang didefinisikan.


\>function f(x) := (x+2/x)/2


Iterasi x(n+1)=f(x(n)) akan konvergen ke akar kuadrat 2.


\>iterate("f",2), sqrt(2)


    1.41421356237
    1.41421356237

Jika pada perintah iterate diberikan tambahan parameter n, maka hasil
iterasinya akan ditampilkan mulai dari iterasi pertama sampai ke-n.


\>iterate("f",2,5)


    [2,  1.5,  1.41667,  1.41422,  1.41421,  1.41421]

Untuk iterasi ini tidak dapat dilakukan terhadap interval.


\>niterate("f",~1,2~,5)


    [ ~1,2~,  ~1,2~,  ~1,2~,  ~1,2~,  ~1,2~,  ~1,2~ ]

Perhatikan, hasil iterasinya sama dengan interval awal. Alasannya
adalah perhitungan dengan interval bersifat terlalu longgar. Untuk
meingkatkan perhitungan pada ekspresi dapat digunakan pembagian
intervalnya, menggunakan fungsi ieval().


\>function s(x) := ieval("(x+2/x)/2",x,10)


Selanjutnya dapat dilakukan iterasi hingga diperoleh hasil optimal,
dan intervalnya tidak semakin mengecil. Hasilnya berupa interval yang
memuat akar persamaan:


$$x = \frac{1}{2} \left( x + \frac{2}{x} \right).$$Satu-satunya solusi adalah


$$x = \sqrt2.$$\>iterate("s",~1,2~)


    ~1.41421356236,1.41421356239~

Fungsi "iterate()" juga dapat bekerja pada vektor. Berikut adalah
contoh fungsi vektor, yang menghasilkan rata-rata aritmetika dan
rata-rata geometri.


$$(a_{n+1},b_{n+1}) = \left( \frac{a_n+b_n}{2}, \sqrt{a_nb_n} \right)$$Iterasi ke-n disimpan pada vektor kolom x[n].


\>function g(x) := [(x[1]+x[2])/2;sqrt(x[1]\*x[2])]


Iterasi dengan menggunakan fungsi tersebut akan konvergen ke rata-rata
aritmetika dan geometri dari nilai-nilai awal.


\>iterate("g",[1;5])


          2.60401 
          2.60401 

Hasil tersebut konvergen agak cepat, seperti kita cek sebagai berikut.


\>iterate("g",[1;5],4)


                1             3       2.61803       2.60403       2.60401 
                5       2.23607       2.59002       2.60399       2.60401 

Iterasi pada interval dapat dilakukan dan stabil, namun tidak
menunjukkan bahwa limitnya pada batas-batas yang dihitung.


\>iterate("g",[~1~;~5~],4)


    Interval 2 x 5 matrix
    
    ~0.999999999999999778,1.00000000000000022~     ...
    ~4.99999999999999911,5.00000000000000089~     ...

Iterasi berikut konvergen sangat lambat.


$$x_{n+1} = \sqrt{x_n}.$$\>iterate("sqrt(x)",2,10)


    [2,  1.41421,  1.18921,  1.09051,  1.04427,  1.0219,  1.01089,
    1.00543,  1.00271,  1.00135,  1.00068]

Kekonvergenan iterasi tersebut dapat dipercepatdengan percepatan
Steffenson:


\>steffenson("sqrt(x)",2,10)


    [1.04888,  1.00028,  1,  1]

# Iterasi menggunakan Loop yang ditulis Langsung

Berikut adalah beberapa contoh penggunaan loop untuk melakukan iterasi
yang ditulis langsung pada baris perintah.


\>x=2; repeat x=(x+2/x)/2; until x^2~=2; end; x,


    1.41421356237

Penggabungan matriks menggunakan tanda "|" dapat digunakan untuk
menyimpan semua hasil iterasi.


\>v=[1]; for i=2 to 8; v=v|(v[i-1]\*i); end; v,


    [1,  2,  6,  24,  120,  720,  5040,  40320]

hasil iterasi juga dapat disimpan pada vektor yang sudah ada.


\>v=ones(1,100); for i=2 to cols(v); v[i]=v[i-1]\*i; end; ...  
\>   plot2d(v,logplot=1); textbox(latex(&log(n)),x=0.5):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-354.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-354.png)

\>A =[0.5,0.2;0.7,0.1]; b=[2;2]; ...  
\>   x=[1;1]; repeat xnew=A.x-b; until all(xnew~=x); x=xnew; end; ...  
\>   x,


         -7.09677 
         -7.74194 

# Iterasi di dalam Fungsi

Fungsi atau program juga dapat menggunakan iterasi dan dapat digunakan
untuk melakukan iterasi. Berikut adalah beberapa contoh iterasi di
dalam fungsi.


Contoh berikut adalah suatu fungsi untuk menghitung berapa lama suatu
iterasi konvergen. Nilai fungsi tersebut adalah hasil akhir iterasi
dan banyak iterasi sampai konvergen.


\>function map hiter(f$,x0) ...


    x=x0;
    maxiter=0;
    repeat
      xnew=f$(x);
      maxiter=maxiter+1;
      until xnew~=x;
      x=xnew;
    end;
    return maxiter;
    endfunction
</pre>
Misalnya, berikut adalah iterasi untuk mendapatkan hampiran akar
kuadrat 2, cukup cepat, konvergen pada iterasi ke-5, jika dimulai dari
hampiran awal 2.


\>hiter("(x+2/x)/2",2)


    5

Karena fungsinya didefinisikan menggunakan "map". maka nilai awalnya
dapat berupa vektor.


\>x=1.5:0.1:10; hasil=hiter("(x+2/x)/2",x); ...  
\>     plot2d(x,hasil):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-355.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-355.png)

Dari gambar di atas terlihat bahwa kekonvergenan iterasinya semakin
lambat, untuk nilai awal semakin besar, namun penambahnnya tidak
kontinu. Kita dapat menemukan kapan maksimum iterasinya bertambah.


\>hasil[1:10]


    [4,  5,  5,  5,  5,  5,  6,  6,  6,  6]

\>x[nonzeros(differences(hasil))]


    [1.5,  2,  3.4,  6.6]

maksimum iterasi sampai konvergen meningkat pada saat nilai awalnya
1.5, 2, 3.4, dan 6.6.


Contoh berikutnya adalah metode Newton pada polinomial kompleks
berderajat 3.


\>p &= x^3-1; newton &= x-p/diff(p,x); $newton


$$x-\frac{x^3-1}{3\,x^2}$$Selanjutnya didefinisikan fungsi untuk melakukan iterasi (aslinya 10
kali).


\>function iterasi(f$,x,n=10) ...


    loop 1 to n; x=f$(x); end;
    return x;
    endfunction
</pre>
Kita mulai dengan menentukan titik-titik grid pada bidang kompleksnya.


\>r=1.5; x=linspace(-r,r,501); Z=x+I\*x'; W=iterasi(newton,Z);


Berikut adalah akar-akar polinomial di atas.


\>z=&solve(p)()


    [ -0.5+0.866025i,  -0.5-0.866025i,  1+0i  ]

Untuk menggambar hasil iterasinya, dihitung jarak dari hasil iterasi
ke-10 ke masing-masing akar, kemudian digunakan untuk menghitung warna
yang akan digambar, yang menunjukkan limit untuk masing-masing nilai
awal.


Fungsi plotrgb() menggunakan jendela gambar terkini untuk menggambar
warna RGB sebagai matriks.


\>C=rgb(max(abs(W-z[1]),1),max(abs(W-z[2]),1),max(abs(W-z[3]),1)); ...  
\>     plot2d(none,-r,r,-r,r); plotrgb(C):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-357.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-357.png)

# Iterasi Simbolik

Seperti sudah dibahas sebelumnya, untuk menghasilkan barisan ekspresi
simbolik dengan Maxima dapat digunakan fungsi makelist().


\>&powerdisp:true // untuk menampilkan deret pangkat mulai dari suku berpangkat terkecil


    
                                     true
    

\>deret &= makelist(taylor(exp(x),x,0,k),k,1,3); $deret // barisan deret Taylor untuk e^x


$$\left[ 1+x , 1+x+\frac{x^2}{2} , 1+x+\frac{x^2}{2}+\frac{x^3}{6}   \right] $$Untuk mengubah barisan deret tersebut menjadi vektor string di EMT
digunakan fungsi mxm2str(). Selanjutnya, vektor string/ekspresi
hasilnya dapat digambar seperti menggambar vektor eskpresi pada EMT.


\>plot2d("exp(x)",0,3); // plot fungsi aslinya, e^x

\>plot2d(mxm2str("deret"),\>add,color=4:6): // plot ketiga deret taylor hampiran fungsi tersebut


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-359.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-359.png)

Selain cara di atas dapat juga dengan cara menggunakan indeks pada
vektor/list yang dihasilkan.


\>$deret[3]


$$1+x+\frac{x^2}{2}+\frac{x^3}{6}$$\>plot2d(["exp(x)",&deret[1],&deret[2],&deret[3]],0,3,color=1:4):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-361.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-361.png)

\>$sum(sin(k\*x)/k,k,1,5)


$$\sin x+\frac{\sin \left(2\,x\right)}{2}+\frac{\sin \left(3\,x  \right)}{3}+\frac{\sin \left(4\,x\right)}{4}+\frac{\sin \left(5\,x  \right)}{5}$$Berikut adalah cara menggambar kurva


$$y=\sin(x) + \dfrac{\sin 3x}{3} + \dfrac{\sin 5x}{5} + \ldots.$$\>plot2d(&sum(sin((2\*k+1)\*x)/(2\*k+1),k,0,20),0,2pi):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-364.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-364.png)

Hal serupa juga dapat dilakukan dengan menggunakan matriks, misalkan
kita akan menggambar kurva


$$y = \sum_{k=1}^{100} \dfrac{\sin(kx)}{k},\quad 0\le x\le 2\pi.$$\>x=linspace(0,2pi,1000); k=1:100; y=sum(sin(k\*x')/k)'; plot2d(x,y):


![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-366.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-366.png)

# Tabel Fungsi

Terdapat cara menarik untuk menghasilkan barisan dengan ekspresi
Maxima. Perintah mxmtable() berguna untuk menampilkan dan menggambar
barisan dan menghasilkan barisan sebagai vektor kolom.


Sebagai contoh berikut adalah barisan turunan ke-n x^x di x=1.


\>mxmtable("diffat(x^x,x=1,n)","n",1,8,frac=1);


            1 
            2 
            3 
            8 
           10 
           54 
          -42 
          944 

![images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-367.png](images/Gita%20Anggi%20Nurlita_22305141004_EMT4Kalkulus-367.png)

\>$'sum(k, k, 1, n) = factor(ev(sum(k, k, 1, n),simpsum=true)) // simpsum:menghitung deret secara simbolik


$$\sum_{k=1}^{n}{k}=\frac{n\,\left(1+n\right)}{2}$$\>$'sum(1/(3^k+k), k, 0, inf) = factor(ev(sum(1/(3^k+k), k, 0, inf),simpsum=true))


$$\sum_{k=0}^{\infty }{\frac{1}{k+3^{k}}}=\sum_{k=0}^{\infty }{\frac{  1}{k+3^{k}}}$$Di sini masih gagal, hasilnya tidak dihitung.


\>$'sum(1/x^2, x, 1, inf)= ev(sum(1/x^2, x, 1, inf),simpsum=true) // ev: menghitung nilai ekspresi


$$\sum_{x=1}^{\infty }{\frac{1}{x^2}}=\frac{\pi^2}{6}$$\>$'sum((-1)^(k-1)/k, k, 1, inf) = factor(ev(sum((-1)^(x-1)/x, x, 1, inf),simpsum=true))


$$\sum_{k=1}^{\infty }{\frac{\left(-1\right)^{-1+k}}{k}}=-\sum_{x=1  }^{\infty }{\frac{\left(-1\right)^{x}}{x}}$$Di sini masih gagal, hasilnya tidak dihitung.


\>$'sum((-1)^k/(2\*k-1), k, 1, inf) = factor(ev(sum((-1)^k/(2\*k-1), k, 1, inf),simpsum=true))


$$\sum_{k=1}^{\infty }{\frac{\left(-1\right)^{k}}{-1+2\,k}}=\sum_{k=1  }^{\infty }{\frac{\left(-1\right)^{k}}{-1+2\,k}}$$\>$ev(sum(1/n!, n, 0, inf),simpsum=true)


$$\sum_{n=0}^{\infty }{\frac{1}{n!}}$$Di sini masih gagal, hasilnya tidak dihitung, harusnya hasilnya e.


\>&assume(abs(x)<1); $'sum(a\*x^k, k, 0, inf)=ev(sum(a\*x^k, k, 0, inf),simpsum=true), &forget(abs(x)<1);


$$a\,\sum_{k=0}^{\infty }{x^{k}}=\frac{a}{1-x}$$Deret geometri tak hingga, dengan asumsi rasional antara -1 dan 1.


\>$'sum(x^k/k!,k,0,inf)=ev(sum(x^k/k!,k,0,inf),simpsum=true)


$$\sum_{k=0}^{\infty }{\frac{x^{k}}{k!}}=\sum_{k=0}^{\infty }{\frac{x  ^{k}}{k!}}$$\>$limit(sum(x^k/k!,k,0,n),n,inf)


$$\lim_{n\rightarrow \infty }{\sum_{k=0}^{n}{\frac{x^{k}}{k!}}}$$\>function d(n) &= sum(1/(k^2-k),k,2,n); $'d(n)=d(n)


$$d\left(n\right)=\sum_{k=2}^{n}{\frac{1}{-k+k^2}}$$\>$d(10)=ev(d(10),simpsum=true)


$$\sum_{k=2}^{10}{\frac{1}{-k+k^2}}=\frac{9}{10}$$\>$d(100)=ev(d(100),simpsum=true)


$$\sum_{k=2}^{100}{\frac{1}{-k+k^2}}=\frac{99}{100}$$# Deret Taylor

Deret Taylor suatu fungsi f yang diferensiabel sampai tak hingga di
sekitar x=a adalah:


$$f(x) = \sum_{k=0}^\infty \frac{(x-a)^k f^{(k)}(a)}{k!}.$$\>$'e^x =taylor(exp(x),x,0,10) // deret Taylor e^x di sekitar x=0, sampai suku ke-11


$$e^{x}=1+x+\frac{x^2}{2}+\frac{x^3}{6}+\frac{x^4}{24}+\frac{x^5}{120  }+\frac{x^6}{720}+\frac{x^7}{5040}+\frac{x^8}{40320}+\frac{x^9}{  362880}+\frac{x^{10}}{3628800}$$\>$'log(x)=taylor(log(x),x,1,10)// deret log(x) di sekitar x=1


$$\log x=-1-\frac{\left(-1+x\right)^2}{2}+\frac{\left(-1+x\right)^3}{  3}-\frac{\left(-1+x\right)^4}{4}+\frac{\left(-1+x\right)^5}{5}-  \frac{\left(-1+x\right)^6}{6}+\frac{\left(-1+x\right)^7}{7}-\frac{  \left(-1+x\right)^8}{8}+\frac{\left(-1+x\right)^9}{9}-\frac{\left(-1  +x\right)^{10}}{10}+x$$