# simpleCipher
### Simple cipher text generator that was built for a school project. It is a modified Ceasar Cipher that uses a Key and pseudo-random letter assignment to encipher a plain  text. Turns a padded key and plain text into numerical values assigned via dictionary, adds the numerical values together, manipulate values to ensure they are within the dictionary limits, output to cipher text. 

### Input: Text file with plain text. Treasure Island by Robert Louis Stevenson is used in this example.

### Output: Ciphered Text

### Key: 1000ce@n5!

### Dictionary
        'a' : '1',
        'b' : '4',
        'c' : '7',
        'd' : '10',
        'e' : '13',
        'f' : '16',
        'g' : '19',
        'h' : '22',
        'i' : '25',
        'j' : '2',
        'k' : '5',
        'l' : '8',
        'm' : '11',
        'n' : '14',
        'o' : '17',
        'p' : '20',
        'q' : '23',
        'r' : '26',
        's' : '3',
        't' : '6',
        'u' : '9',
        'v' : '12',
        'w' : '15',
        'x' : '18',
        'y' : '21',
        'z' : '24',
        '0' : '27',
        '1' : '28',
        '2' : '29',
        '3' : '30',
        '4' : '31',
        '5' : '32',
        '6' : '33',
        '7' : '34',
        '8' : '35',
        '9' : '36',
        '@' : '37',
        '!' : '38' 
				
				
#### Encryption Process
- Takes input, removes any special characters (' ', '\', '.', ',', ';', '-'), change to lowercase.
- Pads key with '@' to match the length of the plain text.
- Assigns characters of padded Key and Plain text, numerical values from the Dictionary.
- Adds the values from these 2 lists together.
- Subtract 25 from all values in list to ensure they are within limit of Dictionary.
- If they are still over limit, subtract 15.
- Assign values in this new list, values from dictionary. Output as string

#### Decryption Process
- Reverse of above
