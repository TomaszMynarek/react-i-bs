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

# Rozwiązany egzamin z galerią zdjeć
```jsx
// Import hooka useState z Reacta – pozwala przechowywać dane w komponencie
import { useState } from 'react'

// Import własnych stylów CSS
import './App.css'

// Import stylów Bootstrap (ładny wygląd)
import 'bootstrap/dist/css/bootstrap.css'

// Główna funkcja aplikacji
function App() {

    // Stan określający, czy mają być pokazane ZWIERZĘTA
    const [showAnimals, setShowAnimals] = useState(true)

    // Stan określający, czy mają być pokazane KWIATY
    const [showFlowers, setShowFlowers] = useState(true)

    // Stan określający, czy mają być pokazane SAMOCHODY
    const [showCars, setShowCars] = useState(true)

    // Stan przechowujący TABLICĘ ZDJĘĆ
    const [photos, setPhotos] = useState([
        // Każdy obiekt to jedno zdjęcie
        { id: 0, alt: "Mak", filename: "obraz1.jpg", category: 1, downloads: 35 },
        { id: 1, alt: "Bukiet", filename: "obraz2.jpg", category: 1, downloads: 43 },
        { id: 2, alt: "Dalmatyńczyk", filename: "obraz3.jpg", category: 2, downloads: 2 },
        { id: 3, alt: "Świnka morska", filename: "obraz4.jpg", category: 2, downloads: 53 },
        { id: 4, alt: "Rotwailer", filename: "obraz5.jpg", category: 2, downloads: 43 },
        { id: 5, alt: "Audi", filename: "obraz6.jpg", category: 3, downloads: 11 },
        { id: 6, alt: "kotki", filename: "obraz7.jpg", category: 2, downloads: 22 },
        { id: 7, alt: "Róża", filename: "obraz8.jpg", category: 1, downloads: 33 },
        { id: 8, alt: "Świnka morska", filename: "obraz9.jpg", category: 2, downloads: 123 },
        { id: 9, alt: "Foksterier", filename: "obraz10.jpg", category: 2, downloads: 22 },
        { id: 10, alt: "Szczeniak", filename: "obraz11.jpg", category: 2, downloads: 12 },
        { id: 11, alt: "Garbus", filename: "obraz12.jpg", category: 3, downloads: 321 }
    ])

    // Tworzymy nową tablicę zdjęć na podstawie zaznaczonych kategorii
    const filteredPhotos = photos.filter(p => {

        // Jeśli zdjęcie jest kwiatem i opcja "Kwiaty" jest włączona – pokaż
        if (p.category === 1 && showFlowers) {
            return true;
        }
        // Jeśli zdjęcie jest zwierzęciem i opcja "Zwierzęta" jest włączona – pokaż
        else if (p.category === 2 && showAnimals) {
            return true;
        }
        // Jeśli zdjęcie jest samochodem i opcja "Samochody" jest włączona – pokaż
        else if (p.category === 3 && showCars) {
            return true;
        }

        // W przeciwnym razie – nie pokazuj zdjęcia
        return false;
    })

    // Funkcja zwiększająca liczbę pobrań zdjęcia
    function updateDownloads(id) {

        // Tworzymy kopię tablicy zdjęć (ważne w React)
        const newPhotos = [...photos]

        // Szukamy zdjęcia o podanym id
        for (const p of newPhotos) {
            if (p.id === id) {
                // Zwiększamy liczbę pobrań o 1
                p.downloads++;
                break;
            }
        }

        // Zapisujemy nową tablicę zdjęć do stanu
        setPhotos(newPhotos)
    }

    // JSX – to, co zobaczymy na stronie
    return (
        <>
            {/* Tytuł strony */}
            <h1>Kategorie zdjęć</h1>

            {/* Checkbox: KWIATY */}
            <div className="form-check form-check-inline form-switch">
                <input
                    type="checkbox"
                    name="flowers"
                    id="flowers"
                    className="form-check-input"
                    checked={showFlowers} // stan checkboxa
                    onChange={() => setShowFlowers(!showFlowers)} // zmiana stanu
                />
                <label htmlFor="flowers" className="form-check-label">Kwiaty</label>
            </div>

            {/* Checkbox: ZWIERZĘTA */}
            <div className="form-check form-check-inline form-switch">
                <input
                    type="checkbox"
                    name="animals"
                    id="animals"
                    className="form-check-input"
                    checked={showAnimals}
                    onChange={() => setShowAnimals(!showAnimals)}
                />
                <label htmlFor="animals" className="form-check-label">Zwierzęta</label>
            </div>

            {/* Checkbox: SAMOCHODY */}
            <div className="form-check form-check-inline form-switch">
                <input
                    type="checkbox"
                    name="cars"
                    id="cars"
                    className="form-check-input"
                    checked={showCars}
                    onChange={() => setShowCars(!showCars)}
                />
                <label htmlFor="cars" className="form-check-label">Samochody</label>
            </div>

            {/* Kontener na zdjęcia */}
            <div className="row">
                {filteredPhotos.map(p => (
                    <div key={p.id} className="col">

                        {/* Wyświetlenie obrazka */}
                        <img
                            src={"assets/" + p.filename}
                            alt={p.alt}
                            className="rounded"
                            style={{ margin: "5px" }}
                        />

                        {/* Liczba pobrań */}
                        <h4>Pobrań: {p.downloads}</h4>

                        {/* Przycisk zwiększający liczbę pobrań */}
                        <button
                            className="btn btn-success"
                            onClick={() => updateDownloads(p.id)}
                        >
                            Pobierz
                        </button>
                    </div>
                ))}
            </div>
        </>
    )
}

// Eksport komponentu, aby mógł być użyty w index.js
export default App

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
# Rozwiazany egzamin z wypisywaniem do konsoli

```jsx
// Import hooka useRef z React – pozwala tworzyć referencje do elementów DOM
import { useRef } from "react"

// Import własnego pliku CSS (wygląd strony)
import "./App.css"

// Import stylów Bootstrap (ładne formularze, przyciski itd.)
import "bootstrap/dist/css/bootstrap.css"

// Główna funkcja aplikacji
function App() {

  // Tablica z nazwami kursów
  const kursy = [
    "Programowanie w C#",
    "Angular dla początkujących",
    "Kurs Django",
  ];

  // Tworzymy referencję do pola Imię i Nazwisko
  const imieNazwiskoRef = useRef();

  // Tworzymy referencję do pola Numer Kursu
  const numerKursuRef = useRef();

  // Funkcja uruchamiana po wysłaniu formularza
  function handleSubmit(event) {

    // Zatrzymuje domyślne odświeżanie strony po wysłaniu formularza
    event.preventDefault();

    // Pobranie wartości z pola Imię i Nazwisko
    const imienazwisko = imieNazwiskoRef.current.value;
    console.log(imienazwisko); // Wyświetlenie w konsoli

    // Pobranie wartości z pola Numer Kursu
    const numerkursu = numerKursuRef.current.value;

    // Pobranie kursu z tablicy na podstawie numeru
    const kurs = kursy[numerkursu - 1]; // -1 bo tablica liczy od 0

    // Sprawdzenie czy kurs istnieje
    if (kurs !== undefined) {
      console.log(kurs); // Wyświetlenie nazwy kursu
    } else {
      console.log("Nieprawidłowy numer kursu"); // Obsługa błędu
    }
  }

  // JSX – to, co zobaczymy na stronie
  return (
    <>
      {/* Wyświetlenie liczby kursów */}
      <h2>Liczba kursów: {kursy.length}</h2>

      {/* Lista kursów w formie numerowanej */}
      <ol>
        {kursy.map((kurs, index) => (
          <li key={index}>{kurs}</li> // Każdy kurs w <li>
        ))}
      </ol>

      {/* Formularz zapisujący do kursu */}
      <form onSubmit={handleSubmit}>

        {/* Pole Imię i Nazwisko */}
        <div className="form-group">
          <label htmlFor="imienazwisko">Imię i nazwisko:</label>
          <input
            type="text"                  // Typ pola – tekst
            id="imienazwisko"            // Id pola
            name="imienazwisko"          // Nazwa pola
            className="form-control"     // Styl Bootstrapa
            ref={imieNazwiskoRef}        // Referencja do pola
          />
        </div>

        {/* Pole Numer Kursu */}
        <div className="form-group">
          <label htmlFor="numerkursu">Numer kursu:</label>
          <input
            type="number"                // Typ pola – liczba
            id="numerkursu"
            name="numerkursu"
            className="form-control"
            ref={numerKursuRef}          // Referencja do pola
          />
        </div>

        {/* Przycisk wysyłający formularz */}
        <div className="form-group mt-3">
          <button type="submit" className="btn btn-primary">
            Zapisz do kursu
          </button>
        </div>

      </form>
    </>
  );
}

// Eksport komponentu App, aby można było użyć go w innych plikach
export default App

```
