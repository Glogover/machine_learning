# Machine Learning – Lecture 1 Notes (EN / PL)

Sep 26, 2026 · @Marcin

## English version

Slides are in lecture order (video timestamps in brackets). Visuals that cannot be retyped are described in square brackets.

### 1. What is Machine Learning (ML)? (1:16)

- Algorithms that automatically improve performance through experience
  - Often this means defining a model by hand, and using data to fit its parameters
- There are problems that are difficult for humans but easy for computers
  - E.g. calculating large arithmetic problems
- And there are problems easy for humans but difficult for computers
  - E.g. recognising a picture of a person from the side
- Machine Learning often tries to leverage the things computers are good at (large arithmetic and repetitive problems) to solve things that we are usually able to do more easily.

### 2. Why ML? (3:56)

- The real world is complex, so it is difficult to hand-craft solutions.
  - Think about how many "if" statements would be needed!
- ML is the preferred framework for applications in many fields:
  - Computer Vision
  - Natural Language Processing
  - Speech Recognition
  - Robotics
- Humans can typically parse sentences, but computers do not get the context.
  - Humans are not consistent with grammar etc., but computers expect consistency.

### 3. Basic Idea of All Machine Learning (6:07)

- Machine Learning is using an **algorithm** that can learn from **data**.
- We want to create a **model** that takes input and gives output. It is basically: **y = f(x)**
- We figure out the right-hand side of the equation by gathering a lot of data and making the parameters best fit our base model.

### 4. Basic Example (8:02)

- Take a base model of y = w0 + w1·x. We need to work out the "best" w0 and w1 parameters.
- Equation of a line: y = mx + c
- &#91;Scatter plot: number of friends (x) vs daily minutes online (y); best fit line Y = 0.9039X + 22.95\]
- Of course, our base model can be much more complicated and have many more parameters that need to be learnt, but the basic idea is the same.
- After we have made the model, we can then make **predictions** in the future. Above, how many daily minutes do we predict for a person with 30 friends on the platform?

### 5. Why Does It Take So Long? (1) (11:37)

- In the above example (one parameter, a basic line as the model), learning all the parameters is very, very quick. But the real world is not that quick.
- Some ML models can take hours, days, weeks or even months to be trained.
  - ChatGPT is actually 8 different models, with 220 billion parameters in each. This takes a very long time to figure out.

### 6. Why Does It Take So Long? (2) (12:28)

- The training is repeatedly doing the same procedure over and over again, until we get the parameters we think are best.
- &#91;xkcd comic: an ML system shown as a pile of linear algebra that you "stir" until the answers look right\]

### 7. Gathering Data (14:50)

- Most of the data we want needs to be *labelled*. This means any data we put into the system is a pair of information: **y, x**
  - where y is the correct answer for each x (which is the collection of all features)
- So, let's say we have a collection of images that are cats or dogs, and we want to build a model that can separate them.
- For a particular image there is a correct y, i.e. y is cat or dog. Then x is all the features of the image, i.e. each x will be the pixel values.

### 8. Dataset Example (17:44)

- We (the human intelligence) must do a lot of work here.
- We need lots of training data and labels associated with them.
- Example: MNIST data set.
  - To learn to recognise handwritten letters, the algorithm must be trained on 60,000 samples, each of which must be labelled correctly, by hand.
- Sample of data set, from Wikipedia. \[grid of handwritten digits 0–9\]

### 9. Hand-Written Digit Recognition (1) (19:55)

- Now let's look at some potential applications and how we could try "phrasing" the problem.
- It is difficult to hand-craft rules about digits. \[examples of messy handwritten digits\]

### 10. Hand-Written Digit Recognition (2) (20:59)

- xᵢ = \[image of a "4"\], yᵢ = (0, 0, 0, 0, 1, 0, 0, 0, 0, 0)
- So, the image can be represented by the value of each pixel. Each pixel colour is called a *feature*, and features are independent variables.
  - Represent the input image as a vector xᵢ ∈ ℝ⁷⁸⁴
  - Suppose we have a target vector tᵢ
    - This is **supervised learning**
    - A discrete, finite label set makes it a **classification** problem.
  - Given a **training set** {(x₁, y₁), …, (x\_N, y\_N)}, the learning problem is to construct a "good" function y = f(x) from these.
    - f: ℝ⁷⁸⁴ → ℝ¹⁰
- Some algorithms will not return exactly (0, 0, 0, 1, …) but may return probabilities like (0.01, 0.03, 0.04, …, 0.01, 0.88 …), so the image is most *likely* a 4.

### 11. Face Detection (23:40)

- &#91;photos with detected faces boxed; Schneiderman and Kanade, IJCV 2002\]
- **Classification** problem.
- tᵢ ∈ {0, 1, 2}: non-face, frontal face, profile face.
- Of course, this can be expanded to the face of a particular person, so the possible tᵢ set could be large.
  - i.e. tᵢ is the set of ALL possible results.
- We **map/transform** the image to a particular tᵢ.

### 12. Stock Price Prediction (25:53)

- Problems in which tᵢ is continuous are called **regression**.
- E.g. tᵢ is the stock price, and xᵢ contains company profit, debt, cash flow, gross sales, number of spam emails sent, …
- &#91;chart: S&P/TSX Composite, May 2006 – Apr 2008\]

### 13. Users of ML (27:22)

- &#91;Logos: Amazon, Netflix, Microsoft, Yahoo!, Gmail, Facebook, Google. Images: CCTV camera, shop receipt, self-driving car, patient vital-signs monitor, brain scans, DNA, video game\]

### 14. High-Profile Examples: Target (29:13)

- Forbes (Kashmir Hill, 16/02/2012): "How Target Figured Out A Teen Girl Was Pregnant Before Her Father Did"

### 15. High-Profile Examples: Netflix (30:21)

- Salon (Andrew Leonard): "How Netflix is turning viewers into puppets". The piece argues that "House of Cards" was built from what Big Data says viewers want.

### 16. High-Profile Examples: Object Recognition (31:05)

- Deep Learning for Object Recognition: Hinton & colleagues, NIPS 2012
- &#91;8 images with the model's top-5 predicted labels, e.g. mite, container ship, motor scooter, leopard\]

### 17. High-Profile Examples: AlphaGo (31:55)

- Learns to play the game Go just by playing games against itself
- Starting from completely random play: https://deepmind.com/blog/alphago-zero-learning-scratch/

### 18. High-Profile Examples: AI Art (32:46)

- Smithsonian SmartNews: "Christie's Is First to Sell Art Made by Artificial Intelligence, But What Does That Mean?"
- Paris-based art collective Obvious' "Portrait of Edmond Belamy" sold for $432,500, nearly 45 times its initial estimate.

### 19. High-Profile Examples: Generative AI (33:08)

- DALL-E
- ChatGPT
- Gemini
- Midjourney
- Etc.

### 20. Supervised Learning (34:03)

- Techniques where we have training examples where we **know** the correct result (the y values). Different types of supervised learning are:
  - Classification
  - Regression
- Some algorithms:
  - Linear/Logistic Regression
  - Naive Bayes
  - k-Nearest Neighbours
  - Support Vector Machines
  - Neural Networks
  - Decision Trees
  - Random Forests

### 21. Unsupervised Learning (34:28)

- Techniques where there is no "right" answer known, but the algorithm tries to find some **structure/patterns** in the data.
  - Principal Component Analysis (Dimensionality Reduction)
  - k-means Clustering
  - PageRank (Google)
- Unsupervised learning techniques will group things together, but we do not necessarily know what the groups are.
- We will do less unsupervised learning in this module.

### 22. Other Types (36:06)

- There are other types of Machine Learning, e.g. Reinforcement Learning.
  - (outside the scope of this module)

### 23. Types of Machine Learning (36:29)

- **Machine Learning**
  - **Supervised Learning**
    - Classification \[plot: two groups of points and an unknown point to assign to one of them\]
    - Regression \[plot: points with a fitted trend line\]
  - **Unsupervised Learning**
    - Clustering \[plot: points grouped into two clusters\]
    - Association \[shapes linked by arrows to show relationships between items\]
  - **Reinforcement Learning**

### 24. Machine Learning (37:23)

- Often referred to as narrow AI.
- We are only concerned with a specific task.
- So the goal of machine learning is not to develop general intelligence or a universal learning algorithm.
- Machine learning seeks an algorithm that learns a particular task well,
- and that should result in a system that probably carries out the task correctly on most occasions.

### 25. What Do We Need to Do Machine Learning? (38:03)

- **The Task:** define or limit the task.
- **The Experience:** this is the data; more data = more experience.
- **The Performance Measure:** we need a good way to measure this.
- **The Learning Algorithm:** the recipe by which we will improve our performance.
- **The Intelligence:** the network, i.e. the brain.

## Wersja polska

Slajdy są w kolejności wykładu (znaczniki czasu nagrania w nawiasach). Elementów graficznych, których nie da się przepisać, dotyczą opisy w nawiasach kwadratowych.

### 1. Czym jest uczenie maszynowe (ML)? (1:16)

- Algorytmy, które automatycznie poprawiają swoje działanie dzięki doświadczeniu
  - Często oznacza to ręczne zdefiniowanie modelu i dopasowanie jego parametrów na podstawie danych
- Istnieją problemy trudne dla ludzi, ale łatwe dla komputerów
  - Np. obliczanie dużych działań arytmetycznych
- Istnieją też problemy łatwe dla ludzi, ale trudne dla komputerów
  - Np. rozpoznanie osoby na zdjęciu z profilu
- Uczenie maszynowe często wykorzystuje to, w czym komputery są dobre (duże obliczenia i powtarzalne zadania), aby rozwiązywać problemy, które nam zwykle przychodzą łatwiej.

### 2. Dlaczego ML? (3:56)

- Świat rzeczywisty jest złożony, więc trudno ręcznie tworzyć rozwiązania.
  - Pomyśl, ile instrukcji „if" byłoby potrzebnych!
- ML to preferowane podejście w wielu dziedzinach:
  - Widzenie komputerowe (Computer Vision)
  - Przetwarzanie języka naturalnego (NLP)
  - Rozpoznawanie mowy
  - Robotyka
- Ludzie zwykle potrafią zrozumieć zdania, ale komputery nie łapią kontekstu.
  - Ludzie nie są konsekwentni w gramatyce itp., a komputery oczekują spójności.

### 3. Podstawowa idea całego uczenia maszynowego (6:07)

- Uczenie maszynowe to użycie **algorytmu**, który potrafi uczyć się z **danych**.
- Chcemy stworzyć **model**, który przyjmuje wejście i zwraca wyjście. W skrócie: **y = f(x)**
- Prawą stronę równania ustalamy, zbierając dużo danych i dobierając parametry tak, by jak najlepiej pasowały do modelu bazowego.

### 4. Prosty przykład (8:02)

- Weźmy model bazowy y = w0 + w1·x. Musimy znaleźć „najlepsze" parametry w0 i w1.
- Równanie prostej: y = mx + c
- &#91;Wykres punktowy: liczba znajomych (x) a dzienne minuty online (y); prosta najlepszego dopasowania Y = 0,9039X + 22,95\]
- Oczywiście model bazowy może być dużo bardziej złożony i mieć znacznie więcej parametrów do nauczenia, ale idea jest ta sama.
- Gdy mamy już model, możemy robić **predykcje** na przyszłość. Ile minut dziennie przewidujemy dla osoby z 30 znajomymi na platformie?

### 5. Dlaczego to trwa tak długo? (1) (11:37)

- W powyższym przykładzie (jeden parametr, prosta jako model) nauczenie wszystkich parametrów jest bardzo, bardzo szybkie. W realnym świecie tak szybko nie jest.
- Trenowanie niektórych modeli ML może trwać godziny, dni, tygodnie, a nawet miesiące.
  - ChatGPT to w rzeczywistości 8 różnych modeli, każdy z 220 miliardami parametrów. Ich wyznaczenie zajmuje bardzo dużo czasu.

### 6. Dlaczego to trwa tak długo? (2) (12:28)

- Trening polega na powtarzaniu tej samej procedury w kółko, aż uzyskamy parametry, które uznamy za najlepsze.
- &#91;Komiks xkcd: system ML jako sterta algebry liniowej, którą „mieszasz", aż odpowiedzi zaczną wyglądać dobrze\]

### 7. Zbieranie danych (14:50)

- Większość potrzebnych danych musi być *oznaczona etykietami*. Oznacza to, że każda dana wprowadzana do systemu to para informacji: **y, x**
  - gdzie y to poprawna odpowiedź dla każdego x (x to zbiór wszystkich cech)
- Załóżmy, że mamy zbiór zdjęć kotów i psów i chcemy zbudować model, który je rozdzieli.
- Dla konkretnego zdjęcia istnieje poprawne y, czyli kot lub pies. x to wszystkie cechy zdjęcia, czyli wartości pikseli.

### 8. Przykładowy zbiór danych (17:44)

- My (ludzka inteligencja) musimy tu wykonać dużo pracy.
- Potrzebujemy dużo danych treningowych wraz z przypisanymi etykietami.
- Przykład: zbiór danych MNIST.
  - Aby nauczyć się rozpoznawać odręczne litery, algorytm musi zostać wytrenowany na 60 000 próbek, z których każda musi być poprawnie oznaczona ręcznie.
- Próbka zbioru danych, z Wikipedii. \[siatka odręcznych cyfr 0–9\]

### 9. Rozpoznawanie odręcznych cyfr (1) (19:55)

- Przyjrzyjmy się potencjalnym zastosowaniom i temu, jak można „sformułować" problem.
- Trudno ręcznie stworzyć reguły opisujące cyfry. \[przykłady niewyraźnych odręcznych cyfr\]

### 10. Rozpoznawanie odręcznych cyfr (2) (20:59)

- xᵢ = \[obraz cyfry „4"\], yᵢ = (0, 0, 0, 0, 1, 0, 0, 0, 0, 0)
- Obraz można przedstawić jako wartości poszczególnych pikseli. Kolor każdego piksela nazywamy *cechą*, a cechy są zmiennymi niezależnymi.
  - Obraz wejściowy reprezentujemy jako wektor xᵢ ∈ ℝ⁷⁸⁴
  - Załóżmy, że mamy wektor docelowy tᵢ
    - To jest **uczenie nadzorowane**
    - Dyskretny, skończony zbiór etykiet oznacza problem **klasyfikacji**.
  - Mając **zbiór treningowy** {(x₁, y₁), …, (x\_N, y\_N)}, problem uczenia polega na zbudowaniu z nich „dobrej" funkcji y = f(x).
    - f: ℝ⁷⁸⁴ → ℝ¹⁰
- Niektóre algorytmy nie zwrócą dokładnie (0, 0, 0, 1, …), lecz prawdopodobieństwa, np. (0,01; 0,03; 0,04; …; 0,01; 0,88 …), więc obraz to *najprawdopodobniej* 4.

### 11. Wykrywanie twarzy (23:40)

- &#91;zdjęcia z zaznaczonymi twarzami; Schneiderman i Kanade, IJCV 2002\]
- Problem **klasyfikacji**.
- tᵢ ∈ {0, 1, 2}: brak twarzy, twarz en face, twarz z profilu.
- Można to rozszerzyć na twarz konkretnej osoby, wtedy zbiór możliwych tᵢ może być duży.
  - Czyli tᵢ to zbiór WSZYSTKICH możliwych wyników.
- **Odwzorowujemy/przekształcamy** obraz na konkretne tᵢ.

### 12. Predykcja cen akcji (25:53)

- Problemy, w których tᵢ jest ciągłe, nazywamy **regresją**.
- Np. tᵢ to cena akcji, a xᵢ zawiera zysk firmy, zadłużenie, przepływy pieniężne, sprzedaż brutto, liczbę wysłanych maili ze spamem, …
- &#91;wykres: indeks S&P/TSX Composite, maj 2006 – kwiecień 2008\]

### 13. Użytkownicy ML (27:22)

- &#91;Logotypy: Amazon, Netflix, Microsoft, Yahoo!, Gmail, Facebook, Google. Obrazy: kamera monitoringu, paragon sklepowy, samochód autonomiczny, monitor funkcji życiowych pacjenta, skany mózgu, DNA, gra komputerowa\]

### 14. Głośne przykłady: Target (29:13)

- Forbes (Kashmir Hill, 16.02.2012): „Jak Target odkrył, że nastolatka jest w ciąży, zanim dowiedział się o tym jej ojciec"

### 15. Głośne przykłady: Netflix (30:21)

- Salon (Andrew Leonard): „Jak Netflix zamienia widzów w marionetki". Artykuł twierdzi, że „House of Cards" zbudowano na tym, czego według Big Data chcą widzowie.

### 16. Głośne przykłady: rozpoznawanie obiektów (31:05)

- Deep Learning w rozpoznawaniu obiektów: Hinton i współpracownicy, NIPS 2012
- &#91;8 zdjęć z 5 najbardziej prawdopodobnymi etykietami modelu, np. roztocz, kontenerowiec, skuter, lampart\]

### 17. Głośne przykłady: AlphaGo (31:55)

- Uczy się gry w Go wyłącznie przez rozgrywanie partii przeciwko sobie
- Zaczynając od całkowicie losowej gry: https://deepmind.com/blog/alphago-zero-learning-scratch/

### 18. Głośne przykłady: sztuka AI (32:46)

- Smithsonian SmartNews: „Christie's jako pierwszy sprzedaje dzieło stworzone przez sztuczną inteligencję. Co to oznacza?"
- „Portret Edmonda Belamy'ego" paryskiego kolektywu Obvious sprzedano za 432 500 USD, prawie 45 razy powyżej początkowej wyceny.

### 19. Głośne przykłady: generatywna AI (33:08)

- DALL-E
- ChatGPT
- Gemini
- Midjourney
- Itd.

### 20. Uczenie nadzorowane (34:03)

- Techniki, w których mamy przykłady treningowe ze **znanym** poprawnym wynikiem (wartości y). Rodzaje uczenia nadzorowanego:
  - Klasyfikacja
  - Regresja
- Przykładowe algorytmy:
  - Regresja liniowa/logistyczna
  - Naiwny klasyfikator Bayesa
  - k-najbliższych sąsiadów (k-NN)
  - Maszyny wektorów nośnych (SVM)
  - Sieci neuronowe
  - Drzewa decyzyjne
  - Lasy losowe

### 21. Uczenie nienadzorowane (34:28)

- Techniki, w których nie znamy „prawidłowej" odpowiedzi, a algorytm próbuje znaleźć w danych jakąś **strukturę/wzorce**.
  - Analiza głównych składowych, PCA (redukcja wymiarowości)
  - Klasteryzacja k-średnich (k-means)
  - PageRank (Google)
- Techniki uczenia nienadzorowanego grupują obiekty, ale niekoniecznie wiemy, czym są te grupy.
- W tym module będzie mniej uczenia nienadzorowanego.

### 22. Inne rodzaje (36:06)

- Istnieją inne rodzaje uczenia maszynowego, np. uczenie ze wzmocnieniem (Reinforcement Learning).
  - (poza zakresem tego modułu)

### 23. Rodzaje uczenia maszynowego (36:29)

- **Uczenie maszynowe**
  - **Uczenie nadzorowane**
    - Klasyfikacja \[wykres: dwie grupy punktów i nieznany punkt do przypisania do jednej z nich\]
    - Regresja \[wykres: punkty z dopasowaną linią trendu\]
  - **Uczenie nienadzorowane**
    - Klasteryzacja \[wykres: punkty pogrupowane w dwa skupiska\]
    - Asocjacja \[figury połączone strzałkami, pokazujące powiązania między elementami\]
  - **Uczenie ze wzmocnieniem**

### 24. Uczenie maszynowe (37:23)

- Często nazywane „wąską AI" (narrow AI).
- Interesuje nas wyłącznie konkretne zadanie.
- Celem uczenia maszynowego nie jest więc stworzenie ogólnej inteligencji ani uniwersalnego algorytmu uczącego się.
- Uczenie maszynowe szuka algorytmu, który dobrze nauczy się konkretnego zadania,
- i powinno dać system, który prawdopodobnie wykona zadanie poprawnie w większości przypadków.

### 25. Czego potrzebujemy, by stosować uczenie maszynowe? (38:03)

- **Zadanie:** zdefiniuj lub ogranicz zadanie.
- **Doświadczenie:** to są dane; więcej danych = więcej doświadczenia.
- **Miara skuteczności:** potrzebujemy dobrego sposobu jej pomiaru.
- **Algorytm uczący:** przepis, według którego poprawiamy skuteczność.
- **Inteligencja:** sieć, czyli „mózg".

## Exam notes / Uwagi do egzaminu

Eight points on the slides are wrong or need a caveat.

- **Slide 4:** the slide text has a word missing ("we need to out the best"). I filled it in as "work out".
- **Slide 5:** the slide says "one parameter", but the line model has two (w0 and w1).
- **Slide 5:** "8 models × 220B parameters" is a 2023 leak about GPT-4. OpenAI never confirmed it, so don't quote it as fact.
- **Slide 8:** MNIST contains handwritten **digits**, not letters.
- **Slide 21:** the slide says "k-mean". The correct name is **k-means**.
- **Slide 21:** PageRank is a graph-ranking algorithm (link analysis), not classic unsupervised learning. If an exam asks for examples, use k-means, PCA or hierarchical clustering.
- **Slide 24:** "probably… on most occasions" most likely refers to PAC learning (*Probably Approximately Correct*).
- **Slide 25:** "The Intelligence – the Network" applies to neural networks. More generally, this is **the model**, which can also be a decision tree, an SVM, and so on.
