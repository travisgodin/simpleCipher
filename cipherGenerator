# -*- coding: utf-8 -*-
"""
Created on Tue Oct  8 22:53:09 2019

@author: Travis Godin
"""
#Takes each char in the string and makes it a list
def split(word):
    return [char for char in word]

#Make the dictionary
#These values are based off a grid pattern
table0 = {
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
        }
#Flip the dictionary to search later
table1 = dict([(value, key) for key, value in table0.items()]) 

#Read the plaintext from a file
infile = open("plain.txt", encoding='utf-8-sig')
plainText = str(infile.read())
infile.close()

#Define the key and plain text
keyPhrase = "1000ce@n5!"

def encrypt(key,plaintext):
    finalList = []
    keyList = []
    plainList = []
    #List variables created
    
    #Clean up the plain text
    plaintext = plaintext.lower()
    plaintext = plaintext.replace(' ', '')
    plaintext = plaintext.replace('\'', '')
    plaintext = plaintext.replace('.', '')
    plaintext = plaintext.replace(',', '')
    plaintext = plaintext.replace(';', '')
    plaintext = plaintext.replace('-', '')

    #Pad the key to match the plain text
    padd = '@' * (len(plaintext)-len(key))
    key = key + padd

    #Assign the values of key to the assigned number in dictionary
    for x in key:
        x = table0[x]
        keyList.append(x)
     
    #Assign the values of plaintext to the assigned number in dictionary
    for y in plaintext:
        y = table0[y]
        plainList.append(y)
     
    #Convert them to integers for manipulation
    plainList = [int(i) for i in plainList]
    keyList = [int(i) for i in keyList]

    #Add the values of the lists together
    change1 = [a+b for a,b in zip(keyList,plainList)]

    #Subract 25, this is to make sure that the max number stays within limits
    change2 = [x-25 for x in change1]
    #If over the scope of the dictionary -15
    change2 = [x-15 if x > 38 else x-0 for x in change2]

    #convert to string so we can search the flipped Dictionary
    change2 = [str(i) for i in change2]

    #Search for the values in the flipped dictionary
    for z in change2:
        z = table1[z]
        finalList.append(z)
        
    #change into string
    cipher = ''.join(finalList)
    
    return cipher

def decrypt(key,ciphertext):
    finalList = []
    keyList = []
    cipherList = []
    
    #Pad the key
    #Key padded because I am still trying figure out how to loop the key to be the length of the plaintext
    padd = '@' * (len(ciphertext)-len(key))
    key = key + padd
    
    #Assign values of Cipher Text to the numbers in Dictionary
    for y in ciphertext:
        y = table0[y]
        cipherList.append(y)
    
    #Assign the values to the key to the assigned number
    for x in key:
        x = table0[x]
        keyList.append(x)
    
    #convert the items to integers
    cipherList = [int(i) for i in cipherList]
    keyList = [int(i) for i in keyList]
    
    #add 25
    change1 = [x+25 for x in cipherList]
    #Subtract values of list from the other
    change2 = [b-a for a,b in zip(keyList,change1)]   
    
    #convert to String
    change2 = [str(i) for i in change2]

    #Compare characters to reversed dictionaries
    for z in change2:
        z = table1[z]
        finalList.append(z)
    
    #Make into String    
    dcipher = ''.join(finalList)
    return dcipher

#Call the encryption
ciphertxt = encrypt(keyPhrase, plainText)
print(ciphertxt)

#Call the decryption
decryptedtxt = decrypt(keyPhrase, ciphertxt)
print(decryptedtxt)

#Write the cipher text file
file = open("ciphertxt.txt", "a+")
file.write(ciphertxt)
file.close()



