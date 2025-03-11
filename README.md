# Animal Quiz App

## 📁 Project Structure

```
app/
├── src/
│   ├── main/
│   │   ├── java/<your_package_name>/
│   │   │   ├── data/
│   │   │   │   ├── db/
│   │   │   │   │   ├── AppDatabase.java           # Room database
│   │   │   │   ├── GalleryDao.java                # Database operations interface
│   │   │   │   └── GalleryItem.java               // Entity for image-name pairs
│   │   │   │   └── GalleryRepository.java         // Repository abstraction
│   │   │   ├── ui/
│   │   │   │   ├── main/
│   │   │   │   │   └── MainActivity.java
│   │   │   │   ├── gallery/
│   │   │   │   │   ├── GalleryFragment.java
│   │   │   │   │   └── GalleryAdapter.java
│   │   │   │   │   └── GalleryViewModel.java
│   │   │   │   └── quiz/
│   │   │   │       ├── QuizFragment.java
│   │   │   │       └── QuizViewModel.java
│   │   │   └── utils/
│   │   │       └── ImageUtils.java
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   ├── activity_main.xml
│   │   │   │   ├── fragment_gallery.xml
│   │   │   │   ├── fragment_quiz.xml
│   │   │   │   └── gallery_item.xml
│   │   │   ├── mipmap/ (app icons)
│   │   │   ├── drawable/ (drawable resources)
│   │   │   ├── values/
│   │   │   │   ├── colors.xml
│   │   │   │   ├── themes.xml
│   │   │   │   └── strings.xml
│   │   │   └── AndroidManifest.xml
│   └── androidTest/
│       └── java/<your_package_name>/
│           ├── GalleryFragmentTest.java
│           └── QuizFragmentTest.java
└── build.gradle
```

## 📚 Explanation

### Data Layer
- **GalleryItem**: Defines a data entity for Room database representing pairs of photos and associated names.
- **GalleryDao**: Provides database operations for CRUD.
- **AppDatabase**: Room database setup.
- **GalleryRepository**: Abstracts database interactions.

### UI Layer
- **MainActivity.java**: Entry-point with navigation to gallery and quiz.
- **GalleryFragment.java**: Manages gallery view and user interactions (add/remove/sort).
- **QuizFragment.java**: Handles quiz logic and UI.

### ViewModel Layer
- **GalleryViewModel.java**: Maintains state for gallery UI.
- **QuizViewModel.java**: Manages quiz state (current question, answers, and score).

### Utils
- **ImageUtils.java**: Contains helper functions for handling image URIs and file operations.

### Layout Resources
- Defined XML layouts for activities and fragments.

### Testing
- Tests located in `androidTest`, including intent stubs and validations of internal states.

---

Replace `<your_package_name>` with your project's actual package name.


