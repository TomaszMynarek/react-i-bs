# Alerts
to komponent służący do wyświetlania komunikatów dla użytkownika, takich jak informacja, sukces, ostrzeżenie lub błąd. Najczęściej używa się go do pokazania wyniku jakiejś akcji, np. zapisania danych albo wystąpienia błędu. Każdy alert musi mieć klasę alert oraz dodatkową klasę określającą jego rodzaj, np. alert-success (sukces), alert-danger (błąd), alert-warning (ostrzeżenie) lub alert-info (informacja). Podstawowy alert wygląda tak:
```html
<div class="alert alert-success" role="alert">
  Dane zapisane poprawnie!
</div>
```
Do alertu można dodawać linki (z klasą alert-link), nagłówki, paragrafy oraz linie oddzielające, co pozwala wyświetlać bardziej rozbudowane komunikaty. Alert może być także zamykany przez użytkownika – w tym celu dodaje się klasy alert-dismissible, fade i show oraz przycisk z klasą btn-close i atrybutem data-bs-dismiss="alert". Przykład zamykanego alertu:
```html
<div class="alert alert-danger alert-dismissible fade show" role="alert">
  Błąd logowania!
  <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
</div>

```
# BUTTONS
to komponent służący do wywoływania akcji (np. wysyłanie formularzy, otwieranie modali, nawigacja). Każdy przycisk musi mieć klasę .btn, która nadaje podstawowy styl, oraz dodatkową klasę wariantu określającą wygląd i znaczenie, np. .btn-primary, .btn-success, .btn-danger. Dostępne są także przyciski obrysowane .btn-outline-*, które nie mają wypełnienia i są używane do mniej istotnych akcji. Rozmiar przycisku można zmienić klasami .btn-lg (duży) i .btn-sm (mały). Przycisk można wyłączyć za pomocą atrybutu disabled (dla <button>) lub klasy .disabled i aria-disabled="true" (dla <a>). Bootstrap pozwala stosować przyciski nie tylko jako <button>, ale także jako <a> i <input>. Przyciski na całą szerokość kontenera tworzy się najczęściej przez d-grid. Dostępne są też przyciski przełączane (toggle), które zmieniają stan po kliknięciu dzięki data-bs-toggle="button".
```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-outline-secondary btn-sm">Anuluj</button>
<button class="btn btn-success btn-lg">Zapisz</button>
<button class="btn btn-danger" disabled>Usuń</button>

<div class="d-grid gap-2 mt-2">
  <button class="btn btn-primary">Przycisk blokowy</button>
</div>

<button class="btn btn-primary mt-2" data-bs-toggle="button">
  Toggle
</button>


```
# BUTTON GROUP
grupuje kilka przycisków w jedną całość (poziomo lub pionowo), dzięki czemu wyglądają i działają jak jeden komponent.

Najważniejsze klasy:
.btn-group – grupa przycisków (pozioma)
.btn-group-vertical – grupa pionowa
.btn – pojedynczy przycisk
.btn-outline-* – przyciski z obramowaniem
.btn-group-sm / .btn-group-lg – rozmiar grupy
role="group" + aria-label – dostępność (ważne na egzamin)
## Przykład prostego kodu
```html
<div class="btn-group" role="group" aria-label="Przykladowa grupa">
  <button type="button" class="btn btn-primary">Lewy</button>
  <button type="button" class="btn btn-primary">Środek</button>
  <button type="button" class="btn btn-primary">Prawy</button>
</div>
```
## Przykład z obramowaniem i rozmiarem
```html 
<div class="btn-group btn-group-sm" role="group" aria-label="Grupa outline">
  <button class="btn btn-outline-secondary">1</button>
  <button class="btn btn-outline-secondary">2</button>
  <button class="btn btn-outline-secondary">3</button>
</div>
```
# CARD
o uniwersalny komponent służący do wyświetlania treści w estetycznym „kafelku”. Używa się go do prezentowania informacji takich jak tytuł, opis, obrazek, lista czy przyciski (np. karta produktu, posta, użytkownika). Podstawą jest kontener .card, a zawartość umieszcza się w .card-body. Card może mieć nagłówek (.card-header), stopkę (.card-footer), obraz (.card-img-top) oraz przyciski i linki. Jest responsywny i łatwy do stylowania klasami Bootstrapa.
## Najprostszy przykład
```html
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Tytuł karty</h5>
    <p class="card-text">Krótki opis zawartości karty.</p>
    <a href="#" class="btn btn-primary">Akcja</a>
  </div>
</div>
```
## Card z obrazkiem
```html
<div class="card" style="width: 18rem;">
  <img src="img.jpg" class="card-img-top" alt="obrazek">
  <div class="card-body">
    <h5 class="card-title">Produkt</h5>
    <p class="card-text">Opis produktu.</p>
  </div>
</div>
```
# Carousel
tCarousel służy do wyświetlania serii slajdów (obrazów, tekstów lub dowolnego HTML-a) w jednym miejscu. Slajdy mogą zmieniać się automatycznie albo po kliknięciu przycisków.

Jak działa:
.carousel – główny kontener,
.carousel-inner – przechowuje slajdy,
.carousel-item – pojedynczy slajd,
jeden slajd MUSI mieć .active, inaczej nic się nie wyświetli,
przyciski carousel-control-prev/next sterują zmianą slajdów,
JavaScript Bootstrapa obsługuje animacje i zdarzenia,

```html
<div id="carouselExample" class="carousel slide">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="img1.jpg" class="d-block w-100" alt="Slide 1"></img>
    </div>
    <div class="carousel-item">
      <img src="img2.jpg" class="d-block w-100" alt="Slide 2"></img>
    </div>
  </div>

  <button class="carousel-control-prev"
          data-bs-target="#carouselExample"
          data-bs-slide="prev">
  </button>

  <button class="carousel-control-next"
          data-bs-target="#carouselExample"
          data-bs-slide="next">
  </button>
</div>
```
# Close button
Close button to uniwersalny przycisk zamykania, np. alertów, modali, toastów.

Jak działa:
.btn-close to tylko ikona przycisku,
sam przycisk nic nie zamyka, musi być użyty wewnątrz komponentu, który obsługuje zamykanie,
aria-label jest wymagany dla dostępności,
```html
<button type="button"
        class="btn-close"
        aria-label="Close">
</button>
```
# Collapse
Collapse umożliwia zwijanie i rozwijanie treści (ukrywanie/pokazywanie elementów).

Jak działa:
element z .collapse jest ukryty,
przycisk lub link z data-bs-toggle="collapse" steruje widocznością,
animacja zmienia height (lub width przy wersji poziomej),
```html
<button class="btn btn-primary"
        data-bs-toggle="collapse"
        data-bs-target="#example"
        aria-expanded="false" 
        aria-controls="collapseExample">
  Pokaż / Ukryj
</button>

<div id="example" class="collapse">
  <div class="card card-body">
    Ukryta treść
  </div>
</div>
```
# Dropdown
Dropdown wyświetla rozwijane menu po kliknięciu przycisku lub linku.

Jak działa:
.dropdown-toggle uruchamia menu,
.dropdown-menu zawiera elementy menu,
Bootstrap używa Popper.js do pozycjonowania,
menu otwiera się po kliknięciu, nie po najechaniu,
```html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle"
          data-bs-toggle="dropdown">
    Menu
  </button>

  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Opcja 1</a></li>
    <li><a class="dropdown-item" href="#">Opcja 2</a></li>
  </ul>
</div>
```
# List group
służy do wyświetlania list elementów (tekstu, linków, przycisków) w spójnym stylu.

Jak działa:
.list-group – kontener,
.list-group-item – pojedynczy element,
.active oznacza aktualnie wybrany element,
.disabled blokuje interakcję,
```html
<ul class="list-group">
  <li class="list-group-item active">Aktywny</li>
  <li class="list-group-item">Element</li>
  <li class="list-group-item">Element</li>
</ul>

```
# Navbar
Navbar to główny pasek nawigacyjny strony, w pełni responsywny.

Jak działa:
.navbar – główny kontener,
.navbar-expand-lg – określa moment zwijania,
.navbar-toggler + Collapse obsługują wersję mobilną,
może zawierać dropdowny, formularze, logo,
```html
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Logo</a>

    <button class="navbar-toggler"
            data-bs-toggle="collapse"
            data-bs-target="#menu">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="menu">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active">Home</a>
        </li>
      </ul>
    </div>
  </div>
</nav>

```
# Progress
Progress pokazuje postęp operacji (np. ładowania).

Jak działa:
.progress to kontener,
.progress-bar to pasek,
szerokość (width) określa procent,
aria-* poprawiają dostępność,
```html
    <div
      className="progress"
      role="progressbar"
      aria-valuenow={60}
      aria-valuemin={0}
      aria-valuemax={100}
    >
      <div
        className="progress-bar"
        style={{ width: "60%" }}
      >
        60%
      </div>
    </div>
```
# Scrollspy
Scrollspy automatycznie podświetla aktywne linki w menu na podstawie pozycji przewijania strony.

Jak działa:
kontener z data-bs-spy="scroll" obserwuje scroll,
data-bs-target wskazuje menu,
linki muszą prowadzić do id sekcji,
```html
<nav id="menu">
  <a href="#sekcja1">Sekcja 1</a>
  <a href="#sekcja2">Sekcja 2</a>
</nav>

<div data-bs-spy="scroll"
     data-bs-target="#menu"
     tabindex="0">
  <h4 id="sekcja1">Sekcja 1</h4>
  <h4 id="sekcja2">Sekcja 2</h4>
</div>

```
