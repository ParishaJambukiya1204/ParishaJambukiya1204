import re

def count_characters_digits_symbols(file_name):
   
    try:
        with open(file_name, 'r') as file:
            text = file.read()
            characters = len(text)
            digits = len(re.findall(r'\d', text))
            symbols = len(re.findall(r'[^\w\s]', text))
            return characters, digits, symbols
    except FileNotFoundError:
        print(f"File '{file_name}' not found.")
        return None

def main():
    file_name = input("Enter the file name: ")
    result = count_characters_digits_symbols(file_name)
    if result:
        characters, digits, symbols = result
        print(f"Characters: {characters}")
        print(f"Digits: {digits}")
        print(f"Symbols: {symbols}")

if __name__ == "__main__":
    main()
