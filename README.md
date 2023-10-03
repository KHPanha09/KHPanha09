- 👋 Hi, I’m @KHPanha09
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
KHPanha09/KHPanha09 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your change
import hashlib
print("**************PASSWORD CRACKER ******************")
         
# To check if the password
# found or not.
pass_found = 0                                 
 
input_hash = input("Enter the hashed password:")
 
pass_doc = input("\nEnter passwords filename including path(root / home/):")
 
try:
    # trying to open the password file.
    pass_file = open(pass_doc, 'r')         
except:
    print("Error:")
    print(pass_doc, "is not found.\nPlease give the path of file correctly.")
    quit()
 
 
# comparing the input_hash with the hashes
# of the words in password file,
# and finding password.
 
for word in pass_file:
    # encoding the word into utf-8 format
    enc_word = word.encode('utf-8')
             
    # Hashing a word into md5 hash
    hash_word = hashlib.md5(enc_word.strip())
 
    # digesting that hash into a hexa decimal value 
    digest = hash_word.hexdigest()      
     
    if digest == input_hash:
        # comparing hashes
        print("Password found.\nThe password is:", word)
        pass_found = 1
        break
 
# if password is not found.
if not pass_found:
    print("Password is not found in the", pass_doc, "file")
    print('\n')
print("***************** Thank you ************
