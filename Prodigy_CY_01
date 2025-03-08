def caesar_cipher(text, shift, mode="encrypt"):
    result = ""
    
    if mode == "decrypt":
        shift = -shift  # Reverse shift for decryption
    
    for char in text:
        if char.isalpha():  # Only shift letters, keep other characters unchanged
            shift_base = ord('A') if char.isupper() else ord('a')
            new_char = chr((ord(char) - shift_base + shift) % 26 + shift_base)
            result += new_char
        else:
            result += char  # Keep non-alphabet characters the same
    
    return result


# User input
message = input("Enter your message: ")
shift_value = int(input("Enter shift value: "))
choice = input("Type 'encrypt' to encrypt or 'decrypt' to decrypt: ").strip().lower()

if choice in ["encrypt", "decrypt"]:
    output = caesar_cipher(message, shift_value, choice)
    print(f"Result: {output}")
else:
    print("Invalid choice. Please type 'encrypt' or 'decrypt'.")
