# Campground Explorer Navigation (Fragments)

This Android application combines two previously built apps — **Parks Explorer** and **Campground Explorer** — into a single application using **Fragments** and **Bottom Navigation**.

Users can browse national parks and campgrounds from the **National Park Service API**, switching between the two views using a bottom navigation bar.

---

## App Demo

![Campground Explorer Navigation Demo](media/CampGroundsFragments.gif)

---

## Features

### Bottom Navigation
The app uses a **BottomNavigationView** to allow users to switch between two sections:

- **Parks**
- **Campgrounds**

Each tab has a custom vector icon.

---

### Fragments
The application dynamically loads fragments inside the main activity:

- `ParksFragment` – Displays a list of national parks
- `CampgroundFragment` – Displays a list of campgrounds

Fragments are swapped using a **FrameLayout container** inside `MainActivity`.

---

### RecyclerView Lists
Both fragments display API data using a **RecyclerView** with adapters:

- `ParksAdapter`
- `CampgroundAdapter`

This allows efficient scrolling and display of park and campground information.

---

### National Park Service API Integration
The application retrieves data from the **National Park Service API**.

Example endpoints used:


https://developer.nps.gov/api/v1/parks

https://developer.nps.gov/api/v1/campgrounds


---

## Project Structure


app
└── src
└── main
└── java/com/codepath/lab6
├── MainActivity.kt
├── ParksFragment.kt
├── CampgroundFragment.kt
├── ParksAdapter.kt
├── CampgroundAdapter.kt
├── Park.kt
└── Campground.kt


---

## Navigation Architecture


MainActivity
│
▼
FrameLayout (Fragment Container)
│
├── ParksFragment
│ └── RecyclerView → ParksAdapter
│
└── CampgroundFragment
└── RecyclerView → CampgroundAdapter


Bottom navigation triggers fragment transactions to replace the current fragment.

---

## How to Run the App

1. Clone the repository


git clone <repo-url>


2. Open the project in **Android Studio**

3. Create a file named:


apikey.properties


Inside the `app` directory and add:


API_KEY=<YOUR_NPS_API_KEY>


4. Run the project using an emulator or Android device.

---

## Technologies Used

- Kotlin
- Android Fragments
- RecyclerView
- BottomNavigationView
- AsyncHttpClient
- Kotlin Serialization
- National Park Service API

---

## Lab Concepts Demonstrated

This lab demonstrates:

- Fragment-based UI architecture
- Dynamic fragment transactions
- Bottom navigation implementation
- RecyclerView data display
- API networking in Android
