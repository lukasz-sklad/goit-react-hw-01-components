# Kryteria zaliczenia

Użyj tego
[szablonu projektu React ](https://github.com/goitacademy/react-homework-template#readme) jako punktu wyjścia dla swojej aplikacji.

* Utworzone zostało repozytorium `goit-react-hw-01-components`.

* Komponenty wszystkich zadań renderują się na jednej stronie, wewnątrz wspólnego kontenera – komponentu root `<App>`.

*  W oddanym zadaniu domowym znajduje się odnośnik do repozytorium z kodem źródłowym projektu.

*  W nagłówku repozytorium znajduje się odnośnik do rzeczywistej strony na `GitHub pages`.

*  Po wejściu na stronę roboczą (GitHub pages) zadania, na konsoli nie ma błędów i ostrzeżeń.

*  Dla każdego komponentu istnieje oddzielny folder z plikiem komponentu React i plikiem stylów.

* Dla wszystkich komponentów opisane są `propTypes`.

*  Wszystko, czego komponent żąda w postaci propsów przekazywane jest do niego przy wywołaniu.

* Nazwy komponentów są zrozumiałe, opisowe.

* Kod JS jest czysty i zrozumiały, wykorzystany został `Prettier`.

* Stylizacja wykonana została `CSS-modułami` lub `Styled Components`, dlatego klasy w ostatecznym DOM będą różnić się od przykładów.

*  Wystarczy bazowa stylizacja aplikacji. Powinna przede wszystkim działać, a dopiero później ładnie wyglądać. Przeznacz 20% czasu na CSS i 80% na JS.


## 1 - Profil w sieci społecznościowej

Należy utworzyć komponent `<Profile>`, przy pomocy którego można wyświetlać informację o użytkowniku sieci społecznościowej. Informacje o użytkowniku znajdują się w pliku 
[user.json](https://downgit.evecalm.com/#/home?url=https://github.com/goitacademy/react-homework/blob/master/homework-01/social-profile/user.json).

![](https://textbook.edu.goit.global/lms-react-homework/v1/pl/img/hw-01/social-profile.png)

## Opis komponentu `<Profile>`

Komponent powinien przyjmować kilka propsów z informacjami o użytkowniku:

* `username` — nazwa użytkownika
* `tag` — tag w sieci społecznościowej `@`
* `location` — miasto i państwo
* `avatar` — odnośnik do awataru
* `stats` — obiekt z informacjami o aktywności

Komponent powinien tworzyć element DOM o następującej strukturze:

```
<div class="profile">
  <div class="description">
    <img
      src="https://cdn-icons-png.flaticon.com/512/1077/1077012.png"
      alt="User avatar"
      class="avatar"
    />
    <p class="name">Petra Marica</p>
    <p class="tag">@pmarica</p>
    <p class="location">Salvador, Brasil</p>
  </div>

  <ul class="stats">
    <li>
      <span class="label">Followers</span>
      <span class="quantity">1000</span>
    </li>
    <li>
      <span class="label">Views</span>
      <span class="quantity">2000</span>
    </li>
    <li>
      <span class="label">Likes</span>
      <span class="quantity">3000</span>
    </li>
  </ul>
</div>
```

### Przykład wykorzystania

```jsx
import user from 'path/to/user.json;

<Profile
  username={user.username}
  tag={user.tag}
  location={user.location}
  avatar={user.avatar}
  stats={user.stats}
/>
```

## 2- Sekcja "statystyki"

Utwórz komponent `<Statistics>`, który wyświetlałby statystyki zgodnie z przekazanymi propsami, na przykład: ładowanie w chmurze zgodnie z rodzajem pliku, odwiedziny strony internetowej przez użytkowników z różnych państw, nakłady finansowe i tym podobne. Informacje o statystykach znajdują się w pliku [data.json](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/goitacademy/react-homework/blob/master/homework-01/statistics/data.json).

![](https://textbook.edu.goit.global/lms-react-homework/v1/pl/img/hw-01/statistics.jpg).

### Opis komponentu `<Statistics>`

Komponent powinien przyjmować dwa propsy `title` i `stats`, w których wyświetla się nagłówek i obiekt statystyk.

* `title` - nie jest obowiązkowy i jeśli nie został przekazany, widok nagłówka nie powinien się renderować `<h2>`.
* `stats` - tablica obiektów zawierających informacje o elemencie statystyki. Może mieć dowolną ilość elementów.
*  Kolor tła elementu statystyki można pominąć albo stworzyć funkcję do generowania losowego koloru.

Komponent powinien tworzyć element DOM o następującej strukturze:

```jsx
<section class="statistics">
  <h2 class="title">Upload stats</h2>

  <ul class="stat-list">
    <li class="item">
      <span class="label">.docx</span>
      <span class="percentage">4%</span>
    </li>
    <li class="item">
      <span class="label">.mp3</span>
      <span class="percentage">14%</span>
    </li>
    <li class="item">
      <span class="label">.pdf</span>
      <span class="percentage">41%</span>
    </li>
    <li class="item">
      <span class="label">.mp4</span>
      <span class="percentage">12%</span>
    </li>
  </ul>
</section>
```

## Przykład wykorzystania

```jsx
import data from '/path/to/data.json';

<Statistics title="Upload stats" stats={data} />
<Statistics stats={data} />
```

## 3 - Lista znajomych

Należy utworzyć komponent `<FriendList>`, przy pomocy którego moglibyśmy wyświetlać informacje o znajomych użytkownika. Dane dotyczące znajomych znajdują się w pliku [friends.json](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/goitacademy/react-homework/blob/master/homework-01/friend-list/friends.json).

![](https://textbook.edu.goit.global/lms-react-homework/v1/pl/img/hw-01/friend-list.jpg)

### Opis komponentu `<FriendList>`

Komponent powinien przyjmować jeden props `friends` – tablicę obiektów przyjaciół.

Komponent powinien tworzyć DOM o następującej strukturze:

```html
<ul class="friend-list">
  <!-- Dowolna ilość FriendListItem -->
</ul>
```

### Opis komponentu `<FriendListItem>`
Komponent powinien przyjmować kilka propsów:

* `avatar` - odnośnika do awataru
* `name` - imię znajomego
* `isOnline` - wartość boolowska informująca o statusie – czy jest w sieci.

W zależności od propsu `isOnline`, powinien zmieniać się kolor tła `span.status`. Można to zrobić poprzez różne klasy CSS lub Styled Components.

Komponent powinien tworzyć DOM o następującej strukturze:

```html
<li class="item">
  <span class="status"></span>
  <img class="avatar" src="" alt="User avatar" width="48" />
  <p class="name"></p>
</li>
```

### Przykład wykorzystania

```jsx
import friends from 'path/to/friends.json';

<FriendList friends={friends} />;
```

## 4 - Historia transakcji

Należy utworzyć komponent historii transakcji na koncie w banku internetowym.

![](https://textbook.edu.goit.global/lms-react-homework/v1/pl/img/hw-01/transactions.jpg)

Dane do listy są dostępne w formacie JSON w pliku [transactions.json](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/goitacademy/react-homework/blob/master/homework-01/transaction-history/transactions.json). To tablica obiektów, na której każdy obiekt opisuje jedną transakcję z następującymi właściwościami:

* `id` — unikalny identyfikator transakcji
* `type` — typ transakcji
* `amount` - kwota transakcji
* `currency` - rodzaj waluty

### Opis komponentu `<TransactionHistory>`

Należy stworzyć komponent `<TransactionHistory>` przyjmujący jeden props `items` – tablicę obiektów transakcji z transactions.json. Komponent tworzy układ tablicy. Każda transakcja to łańcuch tablicy. W przykładzie pokazany został układ dwóch transakcji:

```html
<table class="transaction-history">
  <thead>
    <tr>
      <th>Type</th>
      <th>Amount</th>
      <th>Currency</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Invoice</td>
      <td>125</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>Withdrawal</td>
      <td>85</td>
      <td>USD</td>
    </tr>
  </tbody>
</table>
```

### Przykład wykorzystania

```jsx
import transactions from 'path/to/transactions.json';

<TransactionHistory items={transactions} />;
```