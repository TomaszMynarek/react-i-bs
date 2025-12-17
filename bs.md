# Alerts-to komponent służący do wyświetlania komunikatów dla użytkownika, takich jak informacja, sukces, ostrzeżenie lub błąd. Najczęściej używa się go do pokazania wyniku jakiejś akcji, np. zapisania danych albo wystąpienia błędu. Każdy alert musi mieć klasę alert oraz dodatkową klasę określającą jego rodzaj, np. alert-success (sukces), alert-danger (błąd), alert-warning (ostrzeżenie) lub alert-info (informacja). Podstawowy alert wygląda tak:
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
# BUTTONS-to komponent służący do wywoływania akcji (np. wysyłanie formularzy, otwieranie modali, nawigacja). Każdy przycisk musi mieć klasę .btn, która nadaje podstawowy styl, oraz dodatkową klasę wariantu określającą wygląd i znaczenie, np. .btn-primary, .btn-success, .btn-danger. Dostępne są także przyciski obrysowane .btn-outline-*, które nie mają wypełnienia i są używane do mniej istotnych akcji. Rozmiar przycisku można zmienić klasami .btn-lg (duży) i .btn-sm (mały). Przycisk można wyłączyć za pomocą atrybutu disabled (dla <button>) lub klasy .disabled i aria-disabled="true" (dla <a>). Bootstrap pozwala stosować przyciski nie tylko jako <button>, ale także jako <a> i <input>. Przyciski na całą szerokość kontenera tworzy się najczęściej przez d-grid. Dostępne są też przyciski przełączane (toggle), które zmieniają stan po kliknięciu dzięki data-bs-toggle="button".
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
#BUTTON GROUP-grupuje kilka przycisków w jedną całość (poziomo lub pionowo), dzięki czemu wyglądają i działają jak jeden komponent.

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
#CARD-o uniwersalny komponent służący do wyświetlania treści w estetycznym „kafelku”. Używa się go do prezentowania informacji takich jak tytuł, opis, obrazek, lista czy przyciski (np. karta produktu, posta, użytkownika). Podstawą jest kontener .card, a zawartość umieszcza się w .card-body. Card może mieć nagłówek (.card-header), stopkę (.card-footer), obraz (.card-img-top) oraz przyciski i linki. Jest responsywny i łatwy do stylowania klasami Bootstrapa.
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
