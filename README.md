# Caesar Cipher Project

## Overview

This project is a Python implementation of a simple Caesar Cipher. It allows users to encode or decode messages using a shift cipher technique. The cipher shifts each letter in the text by a specified amount, wrapping around the alphabet as needed.

---

## Features

- Encode messages using a Caesar Cipher.
- Decode messages to retrieve the original text.
- Handles non-alphabetic characters (e.g., numbers, spaces, and symbols) by ignoring them during the encoding/decoding process.
- Allows continuous use with an option to exit the program.

---

## Requirements

- Python 3.x
- `art.py` file for displaying a logo.

---

## How to Use

1. **Run the Program**:
   Ensure that `art.py` is in the same directory as the main program file, and then execute the Python script.

2. **Input Instructions**:
   - Type `encode` to encrypt a message.
   - Type `decode` to decrypt a message.

3. **Provide Message and Shift Value**:
   - Enter the message you want to encode or decode.
   - Enter a numeric value to determine the shift for the cipher.

4. **View Result**:
   The encoded/decoded message will be displayed.

5. **Continue or Exit**:
   - Type `yes` to encode/decode another message.
   - Type `no` to exit the program.

---

## Code Highlights

### Import and Logo

- The `art.py` module is used to display a custom logo when the program starts.

```python
import art
print(art.logo)
```

### Caesar Cipher Function

- Encodes or decodes the provided text based on the shift value and direction (`encode` or `decode`).
- Skips non-alphabet characters to preserve their original positions in the text.

```python
def caesar(original_text, shift_amount, encode_or_decode):
    output_text = ""
    if encode_or_decode == "decode":
        shift_amount *= -1
    elif encode_or_decode == "encode":
        shift_amount = shift
    else:
        print("You did not enter 'encode' or 'decode'.")
        quit()
    for letter in original_text:
        if letter not in alphabet:
            output_text += letter
        else:
            shifted_position = alphabet.index(letter) + shift_amount
            shifted_position %= len(alphabet)
            output_text += alphabet[shifted_position]

    print(f"Here is the {encode_or_decode}d result: {output_text}")
```

### Loop for Multiple Uses

- The program runs continuously until the user opts to exit.

```python
should_continue = True

while should_continue:
    direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n").lower()
    text = input("Type your message:\n").lower()
    shift = int(input("Type the shift number:\n"))

    caesar(original_text=text, shift_amount=shift, encode_or_decode=direction)

    end_game = input("Type 'yes' if you want to continue. Otherwise, type 'no'.\n").lower()
    if end_game == "no":
        should_continue = False
```

---

## Future Improvements

- Add error handling for invalid inputs (e.g., non-numeric shift values or invalid directions).
- Support uppercase letters.
- Provide an option to save encoded/decoded messages to a file.

---

## License

This project is open-source and free to use under the MIT License.

