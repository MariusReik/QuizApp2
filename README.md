
QuizApp
├── app
│   ├── src
│   │   ├── main
│   │   │   ├── java
│   │   │   │   └── com.example.quizapp
│   │   │   │       ├── data
│   │   │   │       │   ├── db
│   │   │   │       │   │   ├── AppDatabase.java          // Room Database-klasse
│   │   │   │       │   │   ├── GalleryItem.java          // Entity for bilde+navn
│   │   │   │       │   │   └── GalleryDao.java           // DAO for database-interaksjon
│   │   │   │       │   └── repository
│   │   │   │       │       └── GalleryRepository.java    // Repository for databaseoperasjoner
│   │   │   │       ├── ui
│   │   │   │       │   ├── gallery
│   │   │   │       │   │   ├── GalleryFragment.java
│   │   │   │       │   │   ├── GalleryAdapter.java
│   │   │   │       │   │   └── GalleryViewModel.java
│   │   │   │       │   ├── quiz
│   │   │   │       │   │   ├── QuizFragment.java
│   │   │   │       │   │   └── QuizViewModel.java
│   │   │   │       │   └── main
│   │   │   │       │       └── MainActivity.java
│   │   │   │       └── utils
│   │   │   │           └── ImageUtils.java               // Hjelpemetoder (håndtere URI/bilder)
│   │   │   ├── res
│   │   │   │   ├── layout
│   │   │   │   │   ├── activity_main.xml
│   │   │   │   │   ├── fragment_gallery.xml
│   │   │   │   │   ├── fragment_quiz.xml
│   │   │   │   │   └── gallery_item.xml
│   │   │   │   ├── drawable
│   │   │   │   │   └── ic_launcher_background.xml
│   │   │   │   ├── values
│   │   │   │   │   ├── strings.xml
│   │   │   │   │   ├── colors.xml
│   │   │   │   │   └── themes.xml
│   │   │   │   └── mipmap (app-ikon)
│   │   │   └── AndroidManifest.xml
│   │   └── test
│   │       └── java
│   │           └── com.example.quizapp (her kommer testene senere)
└── README.md
```

---

## Forklaring av hovedstruktur:

### 📂 `data`-mappe (modell og database):
- **`GalleryItem.java`**
  - Entity som representerer en kombinasjon av navn og bilde (URI til bilde).
- **`GalleryDao.java`**
  - Interface med CRUD-operasjoner mot databasen.
- **`AppDatabase.java`**
  - Definerer Room-database og holder referanse til DAO.
- **`GalleryRepository.java`**
  - Abstraksjonslag mellom ViewModel og databasen.

---

### 📂 `ui`-mappe (aktiviteter, fragments, og ViewModel):

#### ▶️ `main`
- **`MainActivity.java`**
  - Hovedaktivitet med navigasjon til Gallery og Quiz via knapper.

#### 📷 `gallery`
- **`GalleryFragment.java`**
  - Fragment som viser galleri med bilder og navn.
- **`GalleryAdapter.java`**
  - Adapter for å vise GalleryItem-objekter i en RecyclerView.
- **`GalleryViewModel.java`**
  - ViewModel som lagrer og henter data fra databasen via repository.

#### 📝 `quiz`
- **`QuizFragment.java`**
  - Fragment som håndterer quiz-aktiviteten (vise bilde, svarknapper, vise score).
- **`QuizViewModel.java`**
  - Holder quiz-logikken, data (nåværende bilde, svaralternativer, score) og ivaretar tilstand ved skjermrotasjon.

---

### 🔧 `utils`-mappe (hjelpefunksjoner):
- **`ImageUtils.java`**
  - Metoder for enklere håndtering av bilder og URI-konverteringer.

---

### 📂 `res`-mappe (ressurser og layouts):

- **Layouts**: XML-filer for UI-elementer.
  - `activity_main.xml`: Hovedmenyen med navigasjonsknapper.
  - `fragment_gallery.xml`: UI for galleri-visning (RecyclerView med knapper).
  - `fragment_quiz.xml`: UI for quiz (bilde og svar-knapper).
  - `gallery_item.xml`: UI-oppsett for enkelt-element i galleriet (bilde og navn).

---

### ✅ Testmappe for instrumenterte tester (AndroidTest-mappe):

**(Automatisk opprettet av Android Studio når du legger til Espresso/UI-testing)**
```
androidTest
└── java
    └── com.example.projectname
        ├── GalleryFragmentTest.java
        └── QuizFragmentTest.java
```

Her vil du senere plassere tester som:
- Sjekker riktig visning av galleri-elementer.
- Validerer korrekt poengberegning i quiz-modulen.
- Kontrollerer antall elementer etter legg til/slett-operasjoner.

