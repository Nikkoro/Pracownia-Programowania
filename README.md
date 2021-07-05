# Pracownia Programowania

# **Sortowanie bąbelkowe**
Prosta metoda sortowania o złożoności czasowej $O( n^2 )$ i pamięciowej $O(1 ).$

#### **Algorytm działa następująco:**

>W każdym przejściu pętli wewnętrznej porównywane są ze sobą dwie kolejne wartości i w razie potrzemy są zamieniane miejscami. W jednym cyklu pętli wewnętrznej, największa liczba (tak jak bąbelki w napoju gazowanym) w zbiorze będzie się przemieszczała na ostatnią pozycję. W ten sposób otrzymujemy podzbiór częściowo już posortowany. Czynności te powtarzamy dla zbioru pominiętego o elementy już poukładane. 


#### **GIF obrazujący działanie sortowania**

>![bubbleURL](https://upload.wikimedia.org/wikipedia/commons/3/37/Bubble_sort_animation.gif)

#### **Program ilustrujący działanie sortowania bąbelkowego:**


```python
def bubblesort(nums):
    swapped = True
    while swapped:
        swapped = False
        for i in range(len(nums) - 1):
            if nums[i] > nums[i + 1]:
                nums[i], nums[i + 1] = nums[i + 1], nums[i]
                swapped = True
                
a = [int(x) for x in input("Wprowadź liczby do posortowania, oddziel spacjami:").split()]
bubblesort(a)
print(a)
```

    Wprowadź liczby do posortowania, oddziel spacjami:12 312 77 14 15 15 809 299 33 1000
    [12, 14, 15, 15, 33, 77, 299, 312, 809, 1000]
    

# **Największy wspólny dzielnik - Algorytm Euklidesa**

Algorytm Euklidesa służy do wyznaczania największego wspólnego dzielnika. Największy wspólny dzielnik dwóch liczb 

>## $a$  $b$

to taka liczba, która dzieli te liczby i jest ona możliwie największa. Można go zastosować do skracania ułamków lub wyznaczenia najmniejszej wspólnej wielokrotności NWW.

#### **Aby obliczyć NWD$(a,b)$, wykonujemy kolejno następujące kroki:**

>Dzielimy z resztą liczbę $a$ przez liczbę $b$, jeżeli reszta jest równa $0$, to NWD$(a,b)=b$, jeżeli reszta jest różna od $0$, to przypisujemy liczbie $a$ wartość liczby $b$, liczbie $b$ wartość otrzymanej reszty, a następnie ponownie obliczamy $a$ *modulo* $b$.



#### **Program przedstawiający działanie algorytmu Euklidesa:** 



```python
def GCD(a,b):
    if b==0:
        return a
    else:
        return GCD(b,a%b)
    
num1 = int(input("Podaj pierwszą liczbę: "))
num2 = int(input("Podaj drugą liczbę: "))

print("NWD: ", GCD(num1,num2))
```

    Podaj pierwszą liczbę: 123
    Podaj drugą liczbę: 36
    NWD:  3
    

# **Średnia długość wyrazów**

>Program oblicza średnią długość wyrazów , ignorując znaki interpunkcji poprzez zamiane ich na spacje, która jest ignorowana przez funkcję split, co pozwala uzyskać rzetelną średnią długość wyrazów we wprowadzonych zdaniach. Sumowane zostają znaki wyrazów oraz podzielone poprzez liczbę wyrazów. Dla przejrzystośći wynik zostaje zaokrąglony do drugiego miejsca po przecinku.


#### **Program obliczający średnią długość wyrazów w zdaniach:** 


```python
def avgwc(sentence):
    for p in "!?',;.":
        sentence = sentence.replace(p, '')
    words = sentence.split()
    return round(sum(len(word) for word in words)/len(words),2)


sentence1 = input("Wprowadź zdanie nr 1:")
sentence2 = input("Wprowadź zdanie nr 2:")

print(avgwc(sentence1))
print(avgwc(sentence2))
```

    Wprowadź zdanie nr 1:Hello, how are you? I'm under the water... blgpglgpglhh
    Wprowadź zdanie nr 2:Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
    4.56
    5.33
    

# **Źródła z których korzystałem:**

>http://www.algorytm.edu.pl

>https://pl.wikipedia.org/wiki/Algorytm_Euklidesa

