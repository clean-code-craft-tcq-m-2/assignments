# Well-named recap

Always separate tests from regular functionality - E.g., E.g., `testPairToNumber` and `GetColorFromPairNumber`.
Or else all clients of this software will receive test code as well.

[Distinguish unit-testable parts of the manual](https://github.com/clean-code-craft-tcq-m-2/well-named-in-cpp-RicardoGuD/blob/878ff0525db138bcd3bd1b0bd2d94b4ef1d06d26/PrintManual.cpp): Is `getColorNameSizes` easier to test than others? 

Think about testing printManual functionality. All its aspects need to be tested manually.
How could we lower the testing burden?

```cpp
void printManual()
{
    int totalColors = TelCoColor::numberOfMajorColors*TelCoColor::numberOfMinorColors;
    for(int i = 1; i <= totalColors; ++i)
    {
        TelCoColorCoder::ColorPair colorPair = \
            TelCoColorCoder::GetColorFromPairNumber(i);
        std::cout << "Pair " << i << " " << colorPair.ToString() << std::endl;
    }
}
```

---

Examples of easy-to-read file-names:

1. https://github.com/clean-code-craft-tcq-m-2/well-named-in-cpp-RicardoGuD
1. https://github.com/clean-code-craft-tcq-m-2/well-named-in-cpp-FernandoRiv

---

Avoid hard-coding numbers like 25

`for (int number = 1; number <= 25; number++)`

---

Major-minor code repetition

```java
public static MinorColor fromIndex(int index) {
            for(MinorColor color: MinorColor.values()) {
                if(color.getIndex() == index) {
                    return color;
                }
            }
            return null;
        }
```

---

A generic name of the file like `utilities.py` will attract all functionality, growing bigger over time.
