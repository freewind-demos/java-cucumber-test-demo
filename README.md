Java Cucumber Test Demo
=====================

Demo from https://docs.cucumber.io/guides/10-minute-tutorial/

Cucumber是一个BDD测试框架，我们可以在`.feature`文件中，按特定格式来描述测试用例，
然后在某些Java文件中定义与之相对应的代码，然后利用junit来执行并出报告。

`.feature`与`.java`之间是怎么对应上的呢？主要是利用了`@Given/@When`等注解，
以及相应的文字描述（用的是正则匹配字符串），将两者联系在一起。

一个`.feature`中可以包含多个场景`Scenario`，一个`Stepdefs.java`中可以定义多个step。

虽然我们使用了jUnit来运行测试，但是语法并不满足jUnit的定义，所以需要另一个文件来调用
`Cucumber.class`作为Test runner。这个文件需要以`???Test.java`结尾，在cucumber中，
一般写成`runTest.java`，但是也可以写成别的名字，比如`RunCucumberTest`，只要能让`mvn test`
找到即可。

```
mvn test
```