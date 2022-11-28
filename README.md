# **Lab Report 5- Aimee He**

## Code:
```
CPATH=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"
rm -rf student-submission
git clone $1 student-submission
cp TestListExamples.java student-submission
cd student-submission
SCORE=0
if [ -e "ListExamples.java" ]
then
    echo "Correct file! Well done!"
    echo "1 out of 3 points achieved!"
    ((SCORE++))
else
    echo "Wrong file submission!"
    echo "Will remain a" $SCORE"/3 unless you resubmit with correct file name."
    exit
fi
javac -cp $CPATH *.java
if [ $? -ne 0 ]
then
    echo "File did not compile!"
    echo "Will remain a" $SCORE"/3 unless you resubmit fixing compilation error."
    exit
else
    echo "File successfully compiled!"
    echo "2 out of 3 points achieved!"
    ((SCORE++))
fi
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples &> testOutput.txt
if [ $? -eq 0 ]
then
    echo "Tests passed!"
    ((SCORE=SCORE+1))
    echo "Full " $SCORE"/3 points achieved!"
    cat testOutput.txt
    exit
else
    echo "File failed to pass test"
    echo "Will remain " $SCORE"/3 points until all tests are passed"
    cat testOutput.txt
fi
Footer
© 2022 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About

```

## Screenshots:
**Screenshot 1**
![1](https://github.com/meAImee/cse15l-labreport5/raw/main/1.png)

**Screenshot 2**
![2](https://github.com/meAImee/cse15l-labreport5/raw/main/2.png)

**Screenshot 3**
![3](https://github.com/meAImee/cse15l-labreport3/raw/main/3.png)
