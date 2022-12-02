# Reduce complexity - Recap

[Property based tests](https://github.com/clean-code-craft-tcq-m-2/simple-monitor-in-cpp-FernandoRiv/blob/3b5a13b6cca624db61207feb821c99fe8fd293e4/checker_test.cpp) - state the property in the test, instead of example values.

[Data-driven approach](https://github.com/clean-code-craft-tcq-m-2/simple-monitor-in-c-israel-github/blob/17f15440faebdbc6b548c5dbfc07d4e07ae60c78/checker.c)

## Open-close checkpoint

[Conditions nested in code](https://github.com/clean-code-craft-tcq-4/simple-monitor-in-cs-Naveen-R-Mundaganur/blob/8963ae3ed27bbd82cf1c85f2d6045a4dab440162/checker.cs) - but temperature is independent of soc in real-life.
This will cause code to get 'modified' when the customer asks to 'add' the ability to give multiple independent alerts.

Function that can check any of the parameters

```cpp
template <typename paramtype, class Charge_Discharge_SOC_Temp>
bool ChargeTemp_SOC_CRate_Check(paramtype temp_SOC, Charge_Discharge_SOC_Temp ClsName)
```

Separation of consolidation

```cpp
inline bool Combined_Check(bool chargetemp, bool SOC, bool Charge_Rate){
    bool Check_m = (chargetemp && SOC && Charge_Rate);
    return Check_m;
}
```

[One function for all parameters](https://github.com/clean-code-craft-tcq-4/simple-monitor-in-py-harinisuresh2701/blob/14b581d9296479a527474abe40e8bb4c5e1d95d8/check_limits.py)


## Does the name match all of its intent

```c
int IsWithinLimit(float paramValue, const ParamAttributes * param)
{
    if ((paramValue < param->min) || (paramValue > param->max))
    {
        ReportWarningMessage(getOutLimitParamLevel(paramValue, param), param);
        return NOT_IN_LIMIT;
    }
    else
    {
        ReportWarningMessage(getOutLimitParamLevel(paramValue, param), param);
        return IN_LIMIT;
    }
}
```

## Extensions

Tolerance: Good example of naming the 'five percent'

```c
#define INLIMIT_TOLERANCE_PERCENTAGE  (5.0/100.0)
```
(do *not make: `#define FIVE_PERCENT (5.0/100.0)`)

[Single responsibility in data](https://github.com/clean-code-craft-tcq-4/simple-monitor-in-c-pprathi/blob/2c85eac49e73a3aba1f426337516901e97094f1c/BatteryChecker.h)- combining warning-levels with parameters

[Language dictionary](https://github.com/clean-code-craft-tcq-4/simple-monitor-in-py-Aarthi2212/blob/7b663c353f360141296e3f71e47eace9a3b5c6f5/constants.py) defined as constants - how do you test a language?

[Well-organized test cases](https://github.com/clean-code-craft-tcq-4/simple-monitor-in-cpp-vrrenjith5/blob/96a013a377f1375fce81813ac2962407e126095e/main.cpp). Is there an opportunity to reduce the test effort for new parameters?
