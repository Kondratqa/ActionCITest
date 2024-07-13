# ActionCITest
name: Java CI with Maven

on: [push, pull_request]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v4
    - name: Set up JDK 11
      uses: actions/setup-java@v2
      with:
         java-version: '11'
         distribution: 'adopt'
    - name: Build with Maven
      run: mvn -B -e verify
