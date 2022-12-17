# Notepad++ Edifact Macros

EDIFACT is an international standard for Electronic Data Exchange. These macros for Notepad++ are intended to quickly format these messages when working with them.

## Installation

1. Open the shortcuts.xml file located either:
    - In your "C:\Users\{your user}\AppData\Roaming\Notepad++" folder, if you installed Notepad++ using the installer.
    - In the same folder you copied Notepad++ if you are using the portable format.
2. Copy the contents of these macros inside the \<Macros\> XML tag in shortcuts.xml

```xml
    <Macros>
        <!-- Existing macros here -->

        <!-- Copy new macros here> -->
        <Macro name="Edifact - Readable" Ctrl="yes" Alt="no" Shift="yes" Key="69">
            ...
        </Macro>
        <Macro name="Edifact - Condensed" Ctrl="no" Alt="yes" Shift="yes" Key="69">
            ...
        </Macro>
    </Macros>
```

3. Restart Notepad++ so the new macros are loaded.

## What the Macros do

### Edifact - Readable

- **Description:** Format an EDIFACT message whose segments are all on one line so each segment is on its own line. This is based off of the single quote used as the segment terminator.
- **Key Binding:** Ctrl+Shift+E
- **Macro Commands:**
    - Replace:
        - Single quote (ASCII code 39)
    - With:
        - Single quote (ASCII code 39)
        - Carriage Return (ASCII code 13)
        - Line Feed (ASCII code 10)

- **Example:**

```
UNB+IATA+SENDER+RECIP+2212151200+1'UNH+1+EDIMSG:22:1:UN'MSG:1:42'UNT+3+1'UNZ+1+1'
```

```
UNB+IATA+SENDER+RECIP+2212151200+1'
UNH+1+EDIMSG:22:1:UN'
MSG:1:42'
UNT+3+1'
UNZ+1+1'
```

### Edifact - Condensed

- **Description:** Format an EDIFACT message whose segments are all on different lines so the entire message is on one line. This is based off of the single quote used as the segment terminator.
- **Key Binding:** Alt+Shift+E
- **Macro Commands:**
    - Replace:
        - Single quote (ASCII code 39)
        - Carriage Return (ASCII code 13)
        - Line Feed (ASCII code 10)
    - With:
        - Single quote (ASCII code 39)

- **Example:**

```
UNB+IATA+SENDER+RECIP+2212151200+1'
UNH+1+EDIMSG:22:1:UN'
MSG:1:42'
UNT+3+1'
UNZ+1+1'
```

```
UNB+IATA+SENDER+RECIP+2212151200+1'UNH+1+EDIMSG:22:1:UN'MSG:1:42'UNT+3+1'UNZ+1+1'
```

## Changing the Macro Keybinds

If you want to use different keybinds to trigger these macros, change the `Ctrl`, `Alt`, and `Shift` attributes to "yes" and "no" accordingly. Use an ASCII table to look up the decimal value of the character you want to use for the `Key` attribute. For example, the character "uppercase E" is assigned ASCII code 69, whereas "uppercase T" is ASCII code 84.

```xml
<!-- Bind to Ctrl+Shift+E -->
<Macro name="Edifact - Readable" Ctrl="yes" Alt="no" Shift="yes" Key="69">
<!-- Bind to Ctrl+Alt+T -->
<Macro name="Edifact - Readable" Ctrl="yes" Alt="yes" Shift="no" Key="84">
```
