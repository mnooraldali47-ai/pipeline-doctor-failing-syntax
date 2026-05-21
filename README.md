# failing-syntax

## Zweck
Testfall für Pipeline Doctor: **Build schlägt beim Syntax-Check fehl.**

## Erwarteter Fehler
```
  File "main.py", line 6
    def multiply(x, y)
                      ^
SyntaxError: expected ':'
```

## Fehler-Typ
`SyntaxError` — fehlender Doppelpunkt nach `def multiply(x, y)`

## Stage die fehlschlägt
`Syntax Check` — `python -m py_compile main.py` bricht mit Exit-Code 1 ab.
