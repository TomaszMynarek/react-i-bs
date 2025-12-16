# Jak utworzyc aplikacje w react 

Otwieramy terminal przechodzimy tak gdzie chcemy utworzyc aplikacje po czym wpisujemy tak:
```bash 
    npx create-react-app nazwa
```
Po czym wpisujemy:
```bash 
    cd nazwa
    npm start
```
gdy serwer sie uruchomi wchodzimy do przegladarki i wpisuejmy 
## localhost:300

# Aby dodac bs do naszej aplikacji dodajemy 2 linijki w pliku App,js

```jsx
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';

```
teraz juz powinno wszystko dzialac 

# BS

## dodawnie przycisku-wszystkie typy

```jsx
<div className="App">
      <button class="btn btn-primary">Primary</button>
      <button class="btn btn-secondary">Secondary</button>
      <button class="btn btn-success">Success</button>
      <button class="btn btn-danger">Danger</button>
      <button class="btn btn-warning">Warning</button>
      <button class="btn btn-info">Info</button>
      <button class="btn btn-dark">Dark</button>
      <button class="btn btn-light">Light</button>
      <button class="btn btn-link">Link</button>
</div>

```

przycisk bez tła 

```jsx
<div className="App">
    <button class="btn btn-outline-primary">Primary</button>
    <button class="btn btn-outline-success">Success</button>
    <button class="btn btn-outline-danger">Danger</button>
</div>

```

rozmiary przyciskow
```jsx
<div className="App">
    <button class="btn btn-primary btn-lg">Duży</button>
    <button class="btn btn-primary btn-sm">Mały</button>
</div>

```
przycisk w pełnej szerokości
```jsx
<div className="App">
    <button class="btn btn-primary w-100">Na całą szerokość</button>
</div>

```
Przycisk jako link, a lub input
```jsx
<div className="App">
    <a class="btn btn-primary" href="#">Link jako przycisk</a>
    <input class="btn btn-success" type="submit" value="Wyślij"></input>
</div>
```
w znaczniku a atrybut href odpowiada za przekierowywanie

Przyciski grupowane
```jsx
<div class="btn-group">
  <button class="btn btn-primary">1</button>
  <button class="btn btn-primary">2</button>
  <button class="btn btn-primary">3</button>
</div>
```

## listy 

Listy nieuporządkowane (bullet list)
```jsx
<ul class="list-unstyled">
  <li>Element listy</li>
  <li>Element listy</li>
</ul>
```
lub standardowa 
```jsx
<ul>
  <li>Punkt 1</li>
  <li>Punkt 2</li>
</ul>
```
lista opisowa 
```jsx
<dl>
  <dt>Nazwa</dt>
  <dd>Opis tej nazwy</dd>

  <dt>HTML</dt>
  <dd>Język znaczników</dd>
</dl>
```
## List group

podstawowa
```jsx
<ul class="list-group">
  <li class="list-group-item">Element 1</li>
  <li class="list-group-item">Element 2</li>
</ul>
```
Z aktywnym lub wyłączonym elementem:
```jsx
<ul class="list-group">
  <li class="list-group-item active">Aktywny</li>
  <li class="list-group-item disabled">Wyłączony</li>
  <li class="list-group-item">Normalny</li>
</ul>
```
Kolorowe warianty:
```jsx
<ul class="list-group">
    <li class="list-group-item list-group-item-success">OK</li>
    <li class="list-group-item list-group-item-danger">Błąd</li>
    <li class="list-group-item list-group-item-warning">Uwaga</li>
</ul>
```




# Rozwiazany egzamin z wypisywaniem do konsoli

```jsx
// Import pliku CSS z własnymi stylami aplikacji
import './App.css';

// Import gotowych stylów Bootstrap (ładne formularze, przyciski itd.)
import "bootstrap/dist/css/bootstrap.css";

// Główna funkcja aplikacji React
function App() {

  // Funkcja uruchamiana po wysłaniu formularza
  function onSubmit(event) {

    // Zatrzymuje domyślne zachowanie formularza (odświeżenie strony)
    event.preventDefault();

    // Pobiera tekst wpisany w pole input o nazwie "filmTitle"
    const title = event.target.elements.filmTitle.value;

    // Pobiera wybraną wartość z listy select o nazwie "filmType"
    const type = event.target.elements.filmType.value;

    // Wyświetla w konsoli tytuł i rodzaj filmu
    console.log(`tytul: ${title}, rodzaj: ${type}`);
  }

  // Zwracany JSX – czyli to, co zobaczymy na stronie
  return (
    <>
      {/* Formularz, który po wysłaniu wywoła funkcję onSubmit */}
      <form onSubmit={onSubmit} method="post">

        {/* Grupa formularza – tytuł filmu */}
        <div className="form-group">

          {/* Etykieta opisująca pole input */}
          <label htmlFor="filmTitle">Tytuł filmu</label>

          {/* Pole tekstowe do wpisania tytułu filmu */}
          <input
            type="text"              // Typ pola – tekst
            name="filmTitle"         // Nazwa pola (używana w JS)
            id="filmTitle"           // Id pola (łączy się z label)
            className="form-control" // Klasa Bootstrapa dla wyglądu
          />
        </div>

        {/* Grupa formularza – rodzaj filmu */}
        <div className="form-group">

          {/* Etykieta dla listy wyboru */}
          <label htmlFor="filmType">Rodzaj</label>

          {/* Lista rozwijana (select) */}
          <select
            name="filmType"          // Nazwa pola
            id="filmType"            // Id pola
            className="form-control" // Styl Bootstrapa
          >

            {/* Pusta opcja – domyślna */}
            <option></option>

            {/* Opcja: Komedia */}
            <option value="1">Komedia</option>

            {/* Opcja: Obyczajowy */}
            <option value="2">Obyczajowy</option>

            {/* Opcja: Sensacyjny */}
            <option value="3">Sensacyjny</option>

            {/* Opcja: Horror */}
            <option value="4">Horror</option>
          </select>
        </div>

        {/* Grupa z przyciskiem */}
        <div className="form-group">

          {/* Przycisk wysyłający formularz */}
          <button
            type="submit"           // Typ submit – wysyła formularz
            className="btn btn-primary" // Styl Bootstrapa
          >
            Dodaj
          </button>
        </div>

      </form>
    </>
  );
}

// Eksport komponentu App, aby mógł być użyty w innych plikach
export default App;

```
