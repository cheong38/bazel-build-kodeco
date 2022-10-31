# Bazel build tutorial from kodeco

This project is walkthrough from [kodeco bazel tutorial](https://www.kodeco.com/31558158-building-with-bazel/)

## Commands

### Build for iOS

```
$ bazel build //Bullseye-iOS:yourfirstapp
```

### Run for iOS

```
$ bazel run //Bullseye-iOS:yourfirstapp
```

### Build for Android

```
$ bazel build //Bullseye-Android/app/src:yourfirstapp --config=dex
```

### Build JokeGenerator

```
$ bazel build //JokeGenerator:knock_knock
```

### Run JokeGenerator

```
$ bazel run //JokeGenerator:knock_knock
```
