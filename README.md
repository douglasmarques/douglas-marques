# Android showcase
[![CircleCI](https://circleci.com/gh/douglasmarques/showcase-android.svg?style=shield)](https://circleci.com/gh/douglasmarques/showcase-android)
[![Kotlin Version](https://img.shields.io/badge/Kotlin-1.3.72-blue.svg)](https://kotlinlang.org)
[![Gradle](https://img.shields.io/badge/Gradle-5.6.4-blue?style=flat)](https://gradle.org)

[![codebeat badge](https://codebeat.co/badges/ba9fae6e-77d2-4173-8587-36ac8756676b)](https://codebeat.co/projects/github-com-go-ble-ble-master)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/9d1e27b36235434cad003e4ba01e303e)](https://www.codacy.com/manual/douglasmarques/showcase-android?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=douglasmarques/showcase-android&amp;utm_campaign=Badge_Grade)
[![CodeFactor](https://www.codefactor.io/repository/github/douglasmarques/showcase-android/badge)](https://www.codefactor.io/repository/github/douglasmarques/showcase-android)

### MVVM

The app was built using the MVVM (Model-View-View Model) design pattern.

The Model layer represents the data and state of the App, it is represented by classes using the Repository pattern. The repository is responsible for fetching the data from the API and convert it to domain models.

The View layer is represented by Fragments that observe and react to states and actions exposed by the ViewModel.

The ViewModel layer is responsible for interacting with the model and preparing observable data needed by the view. It also provides hooks for the view to pass events to the model. An important thing is that the ViewModel is not tied to the view.
This layer was implemented using JetPack ViewModel and LiveData to expose the observers to the View layer.

### Single Activity App

The app is very simple in terms of navigation and has only one screen, that has a recycler view and display a list of properties.
The app was built using the Navigation Architecture Component to simplify the implementation of the Single Activity concept. It has just one activity and one fragment responsible to display the property list.

### Coroutines

Coroutines were introduced to handle asynchronous calls. They are mainly used to handle the Network calls and they work really well with the JetPack ViewModel and Retrofit.

### Network layer

Retrofit was used to build the network layer because it is a mature library and simple to implement, also is the most used network library across the Android community.
To de/serialize JSON objects was used Moshi. Moshi has adapters and converters that work well with Refrofit and Courotines and also has good performance.

### Unit Tests

Unit tests are covering only the ViewModel and Repository

The unit tests are using two additional test rules to provide the proper executors and dispatchers to the ViewModel (InstantTaskExecutorRule) and Coroutines (CoroutinesTestRule).

## Next-Steps

- Create UI tests using espresso.
- Integrate lint and code style tools to improve the code quality and style.
- Cache data on the repository to avoid extra network calls
- Implement DiffUtils on the recycler view.
