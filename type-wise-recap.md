# Coverage recap

"to be open at the possibility of continuous refactoring with the goal of improving code readability"

"without too much code and just the necessary, keep tests working consistently"

"Use better naming in coding processes."

"avoid duplicate code"

"divide code into smaller modules and make them independent"

## Examples

[Use of factory with injection](https://github.com/clean-code-craft-tcq-m-2/coverage-in-cpp-FernandoRiv/blob/df41883ea081d727f9ebe441a447fbb84e6b74d0/test-alerts.cpp) - see `getBreachHandler` and [its implementation](https://github.com/clean-code-craft-tcq-m-2/coverage-in-cpp-FernandoRiv/blob/df41883ea081d727f9ebe441a447fbb84e6b74d0/typewise-alert.h)

[Functional decomposition](https://github.com/clean-code-craft-tcq-m-2/coverage-in-cpp-RicardoGuD/blob/bb10579605a29fceb6601214c4ad48ad60931ecf/test-alerts.cpp) of the message-formation 

---

Using primitives in strong-typed languages: Reconsider - are you expressing the meaning / purpose of the function?

```java
public static boolean sendToController(BreachType breachType) {
  int header = 0xfeed;
  System.out.printf("%i : %i\n", header, breachType);
  printControllerMsg(breachType, header);
  return true;
}
```

If you cannot test exception condition, it means there is no defined way to handle it. Maybe it should not be handled (caught) here at all?

```cs
catch (Exception) {
    return null;
}
```

What if you had to test the content of the email or the message to the controller, without actually having to see it in an inbox or hardware? How far can you go with unit tests?

