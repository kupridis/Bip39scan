bip39scan - New reliase v 9.9.1 (18/02/2026)
🚀 The fastest brute force mnemonics MultiGPU program in the world! 🚀

Official store of the program https://t.me/cuda8

Update! For those who bought versions 3.2, 4.0.1, 5.5.5, 7.7.7, 8.8.8 the password is the same. 
All future updates and versions will have the same password!


bip39scan v9.9.1 New add:

MODE 12
1. electrum v1
2. electrum v2

MODE 13
1. Solana
2. TON
3. tonlib

MODE 14
1. reads phrases from a file, rearranges words, checks the validity of phrases. --permute -m phrases.txt


MultiGPU program brute force mnemonic phrases
Supports brute force 6, 9, 12, 15, 18, 21, 24 words
The program supports all CUDA cards GeForce (CMP, GTX, RTX...)
Supports multi patch and rmd160 hashes.
 
| GPU card | 24 words | 18 words | 12 words | other brute | Mode 9 BIP32 |
|----------|----------|----------|----------|-------------|--------------|
| RTX 5090 | 250M mnemo/s	| 63M mnemo/s	| 16M mnemo/s | 700k entropy/s | 10M entropy/s |
| RTX 4090 | 160M mnemo/s | 38M mnemo/s	| 11M mnemo/s | 450k entropy/s | 6M entropy/s |
* The speed is indicated when checking 10 addresses in each phrase.
* If you reduce the number of addresses checked, the speed will be higher.
* The size of the address base does not affect the speed +-5%


The program is sold with the source code! cmake Visual Studio 2022 or Linux
The kit includes ready-made programs for Windows x64 and Linux (Ubuntu and hiveos)
To purchase, write to telegram @phrutis2 or buy 24/7 from a bot in a group https://t.me/cuda8


For Linux (Ubuntu, hiveos) 
The commands are the same as for Windows.
You need to add in patch \ before '
chmod +x bip39scan
./bip39scan -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt ...

MODES:

# 1. Sequential search words:
Replace unknown words with \*
Standard random 2048 words in positions with \*
For Linux (Ubuntu) "\*" words "\*" "\*" zoo "\*"  


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt uncover figure script * obscure waste metal quit depend bachelor trust erupt * impose brave leave number rapid oak wealth reopen * noodle tragic

In the phrase, 3 missing words in different positions are replaced by * (test address 14aZB9i8NFiXpeGbS3g7vLArhL7EbNBSWS)

Video https://github.com/user-attachments/assets/e8d4535c-ea78-410f-8ec9-2608847ce975


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt cause ensure shield option monkey infant tray okay remember * * *


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt cause ensure shield option monkey infant tray okay remember * * *


You can use your own list of words from a text file for searching. Only words from the [2048 mnemonic words](https://github.com/phrutis/bip39scan/blob/main/bip39.txt) are supported.
Words in the file must be on a new line. To add a specified list, use -w words.txt Replace unknown words with *

======================================================================================================================================================================================
# 2. Random search words:

bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -w mywordlist.txt -r uncover figure script * obscure waste * quit depend bachelor trust erupt * impose brave leave number rapid oak * reopen * noodle tragic


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -w mywordlist.txt -r uncover figure script * obscure waste * quit depend bachelor trust erupt * impose brave leave number rapid oak * reopen * noodle tragic


https://github.com/user-attachments/assets/2d9d24c7-8844-4de4-9e5d-7eba976d021e

Replace unknown words with \*
Standard random 2048 words in positions with \*
For Linux (Ubuntu) -r "\*" word "\*" zoo   

bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -r cause * shield option monkey infant tray okay remember * * *


bip39scan.exe -a hex160.bin -t HEX --bloom 20482M --save Found.txt --pp pathslist.txt -r cause * shield option monkey infant tray okay remember * * *


Random using your list of mnemonic words from the file words.txt

bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -w words.txt -r cause * shield option monkey infant tray okay remember * * *


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -w words.txt -r cause * shield option monkey infant tray okay remember * * *


For full random, add only stars
Read the question and answer at the bottom of the page
For Linux (Ubuntu) -r "\*" "\*" "\*" "\*" 
Ex. ./bip39scan -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -r "\*" "\*" "\*" "\*" "\*" "\*" "\*" "\*" "\*" "\*" "\*" "\*"

![Image](https://github.com/user-attachments/assets/18393117-eaff-4a81-9eac-46d327207903)


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -r * * * * * * * * * * * *


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -r * * * * * * * * * * * *

======================================================================================================================================================================================
# 3. Reading phrases and passwords from a text file:
The program reads everything from the file: phrases, passwords, passphrases, words, numbers...
There are many finds on them. Supports dictionaries up to 64 TB.

https://github.com/user-attachments/assets/b981b17f-db42-41a7-adb8-3b6dc7d73803


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -m dict.txt


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -m dict.txt


======================================================================================================================================================================================
# 4. Reading phrases and passwords as a stream from an external generator

https://github.com/user-attachments/assets/5d930d3d-4224-4316-8f8f-87a721e21ec8


hashcat.exe --stdout -a 3 -1 ?u?l ?1?l?l?l?d?d?d?d | bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -m stdin


py generator.py | bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -m stdin

======================================================================================================================================================================================
# 5. Reading entropy from a text file
Entropy must be in hex format with a new line.
Depending on the length of the hash, a phrase is created.

Phrase Languages
If not specified, the default will be en
-l en English
-l es Spanish
-l fr French
-l it Italian
-l ja Japanese
-l cs Czech
-l ru Russian
-l uk Ukrainian
-l ko Korean
-l po Portuguese
-l tu Turkish
-l zh_Hans Chinese (Simplified)
-l zh_Hant Chinese (Traditional)

Special lang word NFKD (Normalization Form KD):
-l ja-nfkd Japanese
-l es-nfkd Spanish


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -e entropy.txt


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -e entropy.txt

======================================================================================================================================================================================
# 6. Reading entropy stream from external generator
Now you don't need to modify the program for the next vulnerability.
Create your own generators based on Python or C++ code.
There are many vulnerable random generators on the Internet (github).
Print the entropy in hex format, done.
The program will determine the length of the hex and create a phrase of the required length itself.

Phrase Languages
If not specified, the default will be en
-l en English
-l es Spanish
-l fr French
-l it Italian
-l ja Japanese
-l cs Czech
-l ru Russian
-l uk Ukrainian
-l ko Korean
-l po Portuguese
-l tu Turkish
-l zh_Hans Chinese (Simplified)
-l zh_Hant Chinese (Traditional)

Special lang word NFKD (Normalization Form KD):
-l ja-nfkd Japanese
-l es-nfkd Spanish


https://github.com/user-attachments/assets/df8a0774-307a-46e0-ac01-b9123aad5c50


py entropy.py | bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -e stdin


py entropy.py | bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -e stdin

======================================================================================================================================================================================
# 7. Use the built-in generator passwords
In 2015-2016, there was an online service live.ether where everyone could generate addresses using passwords.
At first https://live.ether.camp they generated from camp 2031 iteration of SHA-3 (Keccak)
then switched to a more secure generation of pbkdf2_hmac_sha512 2048 iterations.
The service worked for about a year and closed, the wallets remained.
live.ether https://github.com/user-attachments/assets/7cba4517-5f2e-4b3a-986a-4cace21cc5fa
Many finds by generator and passwords from file
You can see the list of found passwords 7165 pcs. https://github.com/phrutis/bip39scan/blob/main/Founds.md
In the alpha.txt file, specify your alphabet, numbers, symbols in a line.
The generator works with an increment increasing the password length.

https://github.com/user-attachments/assets/d0fc2faa-b0bb-4f7b-8c4e-575972a0cb26


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --alphabet alpha.txt --start a


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --alphabet alpha.txt --start a


https://github.com/user-attachments/assets/313156e0-d82e-499d-a5c0-644e067d76cd

Every 5 minutes the progress status is written to the file status.txt
To continue, copy the position from status.txt and run --start FromHire1
If there is a space in the start word, run it like this --start "From Hire 1"

Important! The symbols from the starting position must be present in the alphabet.


======================================================================================================================================================================================
# 8. Vulnerable generator libbitcoin explorer v3.2
More about the vulnerability Milk Sad:
RU https://habr.com/ru/articles/771980/
EN https://milksad.info
EN https://milksad.info/disclosure.html#codename-milk-sad
 
bip39scan generates all possible mnemonics across the entire 32-bit
Not everyone knows about this vulnerability. Some sites and applications still use this vulnerable library.
Therefore, the chance to find a fresh coin is very high. Update your address databases.
The main advantage of bip39scan is its high speed!

### The program's operating principle:
When first launched, the program checks all 4294967296 phrases in vulnerable 32 bits of entropy.
After that, the program again goes through 32 bits of entropy but with greater depth, as if the entropy was generated a second time.
Then, the third, fourth ... the program searches indefinitely.
No one has used this method! 
There are finds with a positive balance for it.

https://github.com/user-attachments/assets/8c33254d-46a7-4570-a9e4-3d6d39d87693

Vulnerability 32 bits in each phrase length, in each language from the list. 
Also several patches + different coins. This is for years of searching. 
There are finds with a positive balance

[View 27 finds BTC with positive balance https://github.com/phrutis/bip39scan/blob/main/Founds.md

[Download all empty finds CSV FOUNDS.txt (219к phrases) https://github.com/phrutis/bip39scan/releases/download/4.0.1/FOUNDS.txt

Unix timestamp range (from January 1, 1970, to January 19, 2038).
date/time: 1970-01-01 00:00:00 for first timestamp. If chosen english ETH addresses pach m/44'/60'/0'/0/0-9
it will generate "milk sad ..." mnemonic
<img width="977" height="511" alt="Image" src="https://github.com/user-attachments/assets/c38e79c6-08de-4b5c-8d85-f01f06bf7bba" />

Every 5 minutes the depth position is saved to the file checkpoint.txt
To continue, use the argument --depth 123 (value from the file checkpoint.txt)

Length of phrases
--bits 64 (random phrase 6 words)
--bits 96 (random phrase 9 words)
--bits 128 (random phrase 12 words)
--bits 160 (random phrase 15 words)
--bits 192 (random phrase 18 words)
--bits 224 (random phrase 21 words)
--bits 256 (random phrase 24 words)


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --bits 256


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --bits 128


Phrase Languages
If not specified, the default will be en
-l en English
-l es Spanish
-l fr French
-l it Italian
-l ja Japanese
-l cs Czech
-l ru Russian
-l uk Ukrainian
-l ko Korean
-l po Portuguese
-l tu Turkish
-l zh_Hans Chinese (Simplified)
-l zh_Hant Chinese (Traditional)

Special lang word NFKD (Normalization Form KD):
-l ja-nfkd Japanese
-l es-nfkd Spanish

<img width="978" height="325" alt="Image" src="https://github.com/user-attachments/assets/c3afa204-81df-49a4-9f7f-8b5e17bbdbad" />

<img width="976" height="370" alt="Image" src="https://github.com/user-attachments/assets/e787746a-1646-428c-9865-d62ff85baf66" />


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --bits 192 -l tu


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --bits 256 -l it

======================================================================================================================================================================================
# 9. BIP32
This mode uses hmac_sha512 + salt "Bitcoin seed"
Designed to search for old Bitcoin core and other old BIP32 wallets.
You can make a seed generator https://github.com/hackerschoice/thc-btc-rng-bruteforce based on the old and vulnerable openssl-0.9.8c library https://openssl-library.org/source/old/0.9.x/
This generator https://github.com/abdielsudiro/openssl-entropy was used to create keys and seeds https://cryptodeeptech.ru/vulnerable-openssl/ for the first Bitcoin clients.
Satoshi Nakamoto himself generated keys on this generator!
Ex. from founds: 50 BTC (19 jan 2009)
Adr: 1NChfewU45oy7Dgn51HwkBFSixaTnyakfj https://blockchair.com/ru/bitcoin/address/1NChfewU45oy7Dgn51HwkBFSixaTnyakfj/events/bitcoin-main/1?order=#app-gallery
Key: 5KGLRScL6BqRkWnB8kTtoJmj21GT2W4KHpHJ2AA6vewuqM3tFVM

Recommendations:
1. Using 256 bit hashes for searching.
2. Look for Legacy BTC addresses 1... (there were no other types at the time)
3. Addresses 1... were all UNCOMPRESSED before March 2012!
These are large miner addresses that received 50 BTC per block.
Use uncompressed type: -t P2PKH_UNCOMPRESSED

BIP32 patches:
m/0-5
m/0/0-5
m/0'/0-5
Bitcoin core
m/0'/0-5'
m/0'/0'/0-5'


Reading entropy from file


bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --core entropy.txt


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --core entropy.txt



Receiving entropy from an external generator

py gen.py | bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --core stdin


py generate.py | bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --core stdin


Example founds:

| private key | address | path | entropy (Bitcoin seed) |
|----------|---------------|----------------|----------------|
| L4qs8CTqn4ZY1gJfEgPc1vFpAQNx8wNuF5o9dbM2HhtWnZQKg7an | 1EnXumNo7pyybB9Ntmfsa6S5WbAjsiwLkp | m/3 | e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 |
| L5LxK8WV9wNDemaYBtpEURWi3sHmGsEHpSGmSfahQrreTYKukp9W | 12CL4K2eVqj7hQTix7dM7CVHCkpP17Pry3 | m/0/0 | 000102030405060708090a0b0c0d0e0f101112131415161718191a1b1c1d1e1f |
| KxtynmemHgVetU7rp5MsqSnQ6rvpF7My8DH94Cs7bTH9hwTNn3WL | 15MbJzwHGPq5ETKLBp3yPHoxQ5GUB9avyS | m/0/9 | 000102030405060708090a0b0c0d0e0f0f0e0d0c0b0a09080706050403020100 |


======================================================================================================================================================================================
# 10. BIP32 Brute bip32.org passwords

The bip32.org website has been generating Bitcoin addresses from passwords for over 12 years.
Protection against password brute-force is implemented in the form of 50,000 iterations of the hmac_sha256 password.
This protection significantly slows down the brute-force.
A modern processor i9 (one core) processes about 6 passwords per second.
Which makes brute-force impossible. That's why no one brute-forces these passwords.
The fastest program in the world, bip39scan, processes 60,000 passwords per second on RTX 4090.
Thus, there is a good chance of finding forgotten coins from 10-14 years ago.
Algo: password -> hmac_sha256 (iterations pass) -> hmac_sha512 + salt "Bitcoin seed" -> seed-> ...

Two options for use:
--hmac --iterations 50000
This option takes 1000000 passwords and checks all iterations of the password up to the specified one.
Then takes the next 1 million passwords... (slow search).

--hmac1 --iterations 50000 
Checks only the specified password iteration (as in bip32.org).

Patches:
m/0-9
m/0-1'/0-9
m/0-1'/0-3/0-9

Use multipatch --pp listpathes.txt

 ## Reading passwords from file

bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --hmac1 passwords.txt --iterations 50000


bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --hmac1 passwords.txt --iterations 50000


 ## Receiving passwords from an external generator

py gen.py | bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --hmac1 stdin --iterations 50000


py generate.py | bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt --hmac1 stdin --iterations 50000


Example FOUNDS:

| private key | Address | Path | Password |
|----------|---------------|----------------|----------------|
| KwDqbpxmCjZoWr9EEZ78wqXp14cEH6T4BcqYYhJ825S7PnZpQBjY | 14n1jQ5qYGk3FMY2MVB75C2kUYXD1bs8WJ | m/2 | 7Gusthedog |
| L39kSg5L2pnK3ZHnAQFSidDC5qWXGijQnEi8XjtsUn8k832oZKTT | 1Fq97SgwfLeS27uh6z8gvx8p7Nn4yUzxHm | m/0'/0 | nati1234 |
| L3C3XXFeaNabY1kPce25KQfCU3eVCSRxhrwVS3mfj3vfZqdJPPpB | 1NyifCBG4xVZ45uqc1WWixkWGEDgWQFVWL | m/0'/0 | whiteknight |
| Kwvd9EeCTX67ANa6YNvdiiWxxCUCKFqpeFwst52cbcARfEjTNLod | 17gion6wVJaov65V2RhwwswGUhyARrVf9 | m/0'/0 | sunshine11 |
| L54JNkWKsBXgcrgM8YK9zNdksx3rjATMfeJJ4cYhqY2bfxcdJAKh | 1DTjnc1dW3okt5vcGqSa7DSX3JevbEnk5a | m/0 | yeahyeahyeah |
| KzCtf2HjZu6ECpoiVajierAvyUKZv1Nku7MKtZsDmuHBLMShMMiK | 1FQuvsgTxm6FaynFRWNRP6kGxUHHQiL33Q | m/8 | yeahyeahyeah |
| KzTk56rMTNfXybLNij6g1mVbGkfjK2k8AcfoxSfaRWvAmNjPZYDL | 14SSV31RNNYaDcjw5JB5oHPq6jyg9ssc9H | m/0'/0/8 | password |
| L1TeQekx21Ma8p1w8J46dBMgzWiVzANGSip9sxtBHSBuzxYBSykD | 1782pxsaZczh7tdgjujZVuhB7Dj5z12GdA | m/0'/0/9 | password |


======================================================================================================================================================================================
# 11. Search for Passphrases to Seed Phrases
<img width="1251" height="983" alt="Image" src="https://github.com/user-attachments/assets/7c091ae2-24a8-4833-a549-300fc6f3f433" />
This mode checks the specified list of passphrases (passwords) for each phrase.
Argument --pass dict.txt (passwords on a new line)
Some call this the 13th, 25th word.
In fact, the password is appended to the "mnemonic" salt.

### Passphrases search supports the following modes:

Mode 3 - Reading seed phrases from a text file (Many finds)
bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -m phrases.txt --pass passwords.txt

Mode 4 - Reading phrases as a stream from an external generator
py gen_phrases.py | bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -m stdin --pass passwords.txt

Mode 5 - Reading entropy from a text file
bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt -e entropy.txt --pass passwords.txt

Mode 6 - Reading entropy stream from external generator
py entropy.py | bip39scan.exe -a hex160.bin -t HEX --bloom 2048M --save Found.txt --pp pathslist.txt -e stdin --pass passwords.txt

Mode 8 - Vulnerable generator libbitcoin explorer v3.2
bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --bits 256 --pass passwords.txt

Example FOUNDS:

| SEED phrase | Address | Path | Password |
|----------|---------------|----------------|----------------|
| young where special young fruit clip forum scorpion garden much income patch | [0x6b045a27d6e4eea250dc7526ef378c6c7a3d9de8](https://debank.com/profile/0x6b045a27d6e4eea250dc7526ef378c6c7a3d9de8/history) | m/44'/60'/0'/0/0 | crack |
| total pupil enlist ecology hungry usage weapon guess blade mistake name mouse | [0x835406ef92dedafc55a566b5e53955ce8e85e5a1](https://debank.com/profile/0x835406ef92dedafc55a566b5e53955ce8e85e5a1/history) | m/44'/60'/0'/0/0 | google |
| error equal onion apple pudding kitten zero damp wink mom pudding leg | [0x5e7c985f47b2629a19696d6924ad8bfad88f8b81](https://debank.com/profile/0x5e7c985f47b2629a19696d6924ad8bfad88f8b81/history) | m/44'/60'/0'/0/0 | wrestling |


======================================================================================================================================================================================
# 12. Electrum

bip39scan.exe -a allcoins.bin-t HEX --bloom 8192M --save Found_ELECTRUM_v1.txt -p m/0-1/0-9 --legacy-electrum -m ELECTRUM_OLD_phrases.txt

bip39scan.exe -a allcoins.bin-t HEX --bloom 8192M --save Found_ELECTRUM_v2.txt -p m/0-1'/0/0-9 --electrum -m ELECTRUM_phrases.txt


======================================================================================================================================================================================
# 13. Solana and TON

Solana: два режима. обычный bip32 режим (современный) и legacy-режим (путь 'm'). 
Т.е. когда путь m - работает старая деривация, а не bip32 деривация. Нужно передать -t solana.
TON: тоже два режима. Первый - tonlib, стандартная тоновская деривация, которая не bip39 и не bip32. 
Путей там нет, поэтому этот режим включается отдельным флагом --tonlib: 

bip39scan.exe -a ton-pubkeys.txt -m phrases.txt --tonlib

bip39scan.exe -a ton-pubkeys.txt -m phrases.txt --tonlib --pass pwd.txt

Второй режим - ed25519 деривация с bip39/bip32, которая есть в некоторых кошельках, например trezor и ledger. 
Этот режим включается опцией -t ton, например:

bip39scan.exe -a ton-pubkeys.txt -m phrases.txt -t ton --pp paths.txt

bip39scan.exe -a ton-pubkeys.txt -m phrases.txt -t ton --pp paths.txt --pass pwd.txt

где paths.txt содержит например:
m/44'/607'/0'/0-10'/0-10'
m
m/0-1'

И solana, и ton поддерживают только hardened деривацию, т.е. пути с '

--tonlib очень медленный - 100000 итераций


======================================================================================================================================================================================
# 14. Permutation

bip39scan.exe -a allcoins.bin -t HEX --bloom 8192M --pp paths.txt --permute -m phrases.txt

Mnemonics must contain valid BIP39 words, otherwise there will be an error.




# Other sections:

## Download ready-made address databases for bip39scan

ALL ETH + ALL TOKENS + ALL BTC + history = 2.775.909.490 addresses
Doesn't start on 12 GB cards!!! The database fits on a 16 GB card or more!!! 
To run you need 52 GB of RAM 
Add these arguments to run --bloom 8192M -t HEX
Download http://95.215.108.160/up/allcoins.bin  53 GB

TRON TRX + history = 150M addresses
Add these arguments to run --bloom 2048M -t HEX
Download http://95.215.108.160/up/tron.bin  3 GB

ALL ETH 1458757703 addresses with balance 09/07/2025 + empty + ALL ETH TOKENS with balance 09/07/2025 + empty history:
ARBITRUM, AVALANCHE, BASE, BNB, BSC, BTT, CRONOS, CELO, ETC, Ethereumnie, ERA, ERC20, ETH, Ethered, FANTOM, 
GETH (Goerli), GNOSIS, IOTX, LINEA, MOONBEAM, MOONRIVER, OPBNB, OPTIMISM, POLYGON, VET, ZKEVM-POLYGON...
Doesn't start on 8 GB cards! The database fits on a 12 GB card or more. 
To run you need 32 GB of RAM (if you don't have that much, you can use the swap file) 
Add these arguments to run --bloom 4096M -t ethereum
Download http://95.215.108.160/up/alleth.bin  29 GB

ALL BTC addresses 1... P2PKH with balance + empty (history)
Add these arguments to run --bloom 2048M -t P2PKH
Download http://95.215.108.160/up/allbtc1.bin  11.9 GB

ALL BTC addresses 3... P2SH with balance + empty (history)
Add these arguments to run --bloom 2048M -t P2SH
Download http://95.215.108.160/up/allbtc3.bin  7.6 GB

ALL BTC addresses bc1q... bech32 with balance + empty (history)
Add these arguments to run --bloom 2048M -t bech32
Download http://95.215.108.160/up/allbc.bin  6.5 GB

## Addresses only with positive balance

Download ETH + BTC 1.., 3.., bc... from $1 (up 01.11.2025)
-a hex160.bin -t HEX
http://95.215.108.160/up/hex160.bin  2.6 GB

Download BTC addresses 1... 30/06/2025
http://95.215.108.160/up/btc1.txt  787 MB

Download BTC addresses 3... 30/06/2025
http://95.215.108.160/up/btc3.txt 240 MB

Download BTC addresses bc... 30/06/2025
http://95.215.108.160/up/bc.txt 842 MB

I recommend using large address bases.
For example, BCH may remain on the historical address 1... (P2PKH)

Launching the program with a text database of addresses.
Each address must be on a new line!
The text address base is well suited for quick tests

bip39scan.exe --save Found.txt -a btc1.txt -t P2PKH -p m/44'/0'/0'/0/0-9 --bits 256
bip39scan.exe --save Found.txt -a btc3.txt -t P2SH -p m/49'/0'/0'/0/0-9 --bits 256
bip39scan.exe --save Found.txt -a btc-bc.txt -t bech32 -p m/84'/0'/0'/0/0-9 --bits 256
bip39scan.exe --save Found.txt -a eth_addresses.txt-t ethereum -p m/44'/60'/0'/0/0-9 --bits 256

## Create your own .bin database from addresses

To avoid waiting for a long time for the addresses to be loaded into the program.
Create and use binary databases.
The program will start in seconds
Create databases:
BTC
bip39scan.exe --save Found.txt -a btc1.txt -t P2PKH --save-bin btc1.bin --bloom 2048M --pp pathslist.txt --bits 256
bip39scan.exe --save Found.txt -a btc3.txt -t P2SH --save-bin btc3.bin --bloom 2048M --pp pathslist.txt --bits 256
bip39scan.exe --save Found.txt -a btc-bc.txt -t bech32 --save-bin bc.bin --bloom 2048M --pp pathslist.txt --bits 256

ETH and tokens
bip39scan.exe --save Found.txt -a eth_addresses.txt --save-bin eth.bin -t ethereum --bloom 4096M --pp pathslist.txt --bits 256

HEX base 160
Hashes160 must be on a new line in text format!
bip39scan.exe -a hashes160.txt -t HEX --bloom 8192M --save Found.txt --pp pathslist.txt --save-bin new_hex160.bin --bits 256

Text file more 12 GB USE --bloom 2048M
Text file more 50 GB USE --bloom 4096M
Text file more 120 GB USE --bloom 8192M

Next launches run like this! 
bip39scan.exe --save Found.txt -a allcoins.bin -t HEX --bloom 8192M --pp pathslist.txt --bits 256
bip39scan.exe --save Found.txt -a hex160.bin -t HEX --bloom 2048M --pp pathslist.txt --bits 256

bip39scan.exe --save Found.txt -a btc1.bin -t P2PKH --bloom 2048M --pp pathslist.txt --bits 256
bip39scan.exe --save Found.txt -a btc3.bin -t P2SH --bloom 2048M --pp pathslist.txt --bits 256
bip39scan.exe --save Found.txt -a bc.bin -t bech32 --bloom 2048M --pp pathslist.txt --bits 256
bip39scan.exe --save Found.txt -a alleth.bin --bloom 4096M -t ethereum --pp pathslist.txt --bits 256


Where can I download a fresh database of addresses?
BTC and other coins https://blockchair.com/dumps
Fresh ETH addresses + ETH Tokens taken from node dumps
https://routescan.io/dumps?page=2&nexttoken=undefined
Each address must be on a new line.
Ethereum addresses must be 0x...
Bitcoin addresses 1.., 3.., bc.. (New long addresses bc.. does not accept)

# FAQ
The program did not find my test password from the file.

Do not use small dictionaries for the test.
The program starts in 3-5 seconds, at a speed of 500k, it can go through your dictionary of 25 phrases in 0.001 sec and finish the work without having time to give the result.
I recommend using dictionaries from 5 million lines and more.
The program has 65536 threads, while 50 threads processed your list, other threads (65511 empty) without load finished the program earlier.<hr>

My random finds the same thing!?

In old versions of the program (v2.0.1, v3.2) with each new launch for random, 
you need to additionally specify initialization for the generator.
--seed + 8 random digits.
Example:
--seed 87659645 -r * * * * * * * * * * * * 
--seed 96537996 -r * * * * * * * * * * * * 
If you do not specify the starting seed, the default seed 0 will be used
-r * * * * * * * * * * * * 
You will go through all the time from the beginning (previously passed).

In versions: (4.0.1), (4.1.2), (5.0.1) you do not need to do this!
The program itself randomizes the starting seed<hr>

What is the difference between --hmac and --hmac1 in mode 10?

``--hmac`` checks addresses in each password iteration.
You specified 50,000 iterations.
The program takes 1,000,000 passwords
It will check the seed in the first iteration, in the second ... the 50,000th.

In total, for one password it will generate 50k seeds with address checking.
It needs to check 1,000,000 x 50,000 = 50,000,000,000 seeds.
Your speed is 5M - you need 2 hours 45 minutes to check

``--hmac1`` checks addresses only in the specified iteration.
It takes 1,000,000 passwords, makes iterations and does not check the seed until the specified one.
Your speed is 60k
1000000/60000 = it will take you 15 seconds to check<hr>

The program doesn't start for me and doesn't display bip39scan -h

There is no OpenCL on your PC!
Install the required library:
https://slproweb.com/download/Win64OpenSSL-3_0_17.msi
https://aka.ms/vs/17/release/vc_redist.x64.exe
<hr>

How to check the found HEX160?

Example founds:
c0a95cc48dcfb76f02edf0ff020f8ccc44da576d(ethereum) -> 0xc0a95cc48dcfb76f02edf0ff020f8ccc44da576d
For BTC:
aa6b6bdfc262fe316db3c83aec84177b750d985a(P2PKH_UNCOMPRESSED)
aa6b6bdfc262fe316db3c83aec84177b750d985a(P2PKH) - Address 1.. or see path if m/84.. bc..
71fc5be17c98a1e6018be06d1dfe8f41eafee51e(P2SH)
Use a quick script to generate addresses from private keys
py gen_address.py or python3 gen_address.py
Paste the found private key
<hr>

How do I convert my addresses to 160 hashes?

Use Python addto160.py
Incoming address file - adr.txt
Outgoing file - hex160out.txt
Supports BTC addresses 1.., 3.., bc..
For ETH addresses and tokens, remove the 0x
<hr>

How to change the derivation in a patch?

You can set a non-standard patch derivation at your discretion:
m/0-9
m/0/0-9
m/0/0/0-9
m/0-99/0-99/0-99
m/44'/0-99'/0'/0/0-9
m/0-99'/0-99'/0'/0-5/0-999
max value: 2147483647
Where is ' - max value: 4294967296
m/44'/0-4294967296'/0-4294967296'/0-2147483647/0-2147483647<hr>

Tell me patches of different coins

[Full list of patches BIP32, BIP39](https://github.com/phrutis/bip39scan/blob/main/Patches.md)<hr>

How to create a patch file?

Create a text file and rename it, for example, to pathes.txt
Insert the list of required paths on a new line.
m/44'/60'/0'/0/0-9
m/44'/0'/0'/0-1/0-9
m/49'/0'/0'/0/0-9
m/84'/0'/0'/0/0-9
USE --pp pathes.txt
<hr>

Why do we need streams, generators?
How does it work? Show an example.

Most random generators are vulnerable.
If you have the knowledge to write code.cu to embed a generator, you wouldn't ask such a question.
Even if you have such knowledge, it's easier and faster to write a three-line python code, done!
Changing the program for each generator is not rational.
It's easier to find a phrase by vulnerability than to endlessly brute-force emptiness.
[Examples of generators](https://github.com/phrutis/bip39scan/blob/main/Generators/README.md)<hr>

I don't understand what entropy is?

[SEE HIRE](https://learnmeabitcoin.com/technical/keys/hd-wallets/mnemonic-seed/)<hr>

bro, write me a generator so that it spins like this and then like that...
I'm a newbie, I don't understand programming, help.

For these purposes, find an AI bot.
Now bots have become very smart, they write programs and scripts.
Write to the bot what you need to do, spin and how.<hr>

My program won't start - bloom memory error...?

Take a screenshot of the program window and send it to me.

99% you made a mistake in the launch command.
Most likely you did not specify the memory size for the filter.
Base.bin 7 GB+ specify --bloom 2048M
Base.bin 20 GB+ specify --bloom 4096M
Base.bin 50 GB+ specify --bloom 8192M<hr>

Where can I make a mnemonic from a password?

Online generator http://95.215.108.160
Bookmark this<hr>

What is precomp.bin?

This is a table of acceleration, pre-calculated points of the curve<hr>

Words and letters from the previous generation remain (stick) in my window, how can I fix it?

Languages or some characters may also be displayed incorrectly. 
These are properties of the correction and different language encodings.
This does not affect the brute force process itself.<hr>

What mode is better to search in? Where are there more prospects? Where and how much did you find?

Try different modes and directions.
Search in the one in which you think you have the best chance of finding.
Finds are found, they are not asked about, and they are not told. When you find one, will you tell everyone?<hr>

How can I search for other coins like Salona?

Create several test addresses.
Convert addresses to ripemd160 hashes.
Be sure to sort 00...ff
Run the program, specify the type, for example for BTC -t P2PKH
The program will find an empty address BTC 1.... you don't need it.
Take the phrase, or private key, generate the address of the desired coin
If you do everything correctly, you will find test addresses<hr>

Why specify -t typecoin ?

When you search with binary database the program does not know what coin you are looking for.
BE SURE TO SPECIFY - t typecoin
Use a specific type: P2SH, P2PKH_UNCOMPRESSED, P2PKH, bech32, ethereum
Or use the HEX type for all coin types
<hr>

What does -t HEX look for?

By specifying this type, you are searching for 5 types of coins at once.
BTC P2PKH
BTC P2PKH_Uncompressed
BTC P2SH
BTC Bech32 p2pkh
ETH
The program searches for 160 hashes from addresses, you can add 160 hashes from other coins.<hr>

## bip39scan.exe -h
bip39scan v9.9.1 (phrutis modification 18/02/2026) t.me/cuda8
Bruteforce bip39 mnemonics
Syntax: bip39scan [OPTIONS] [MNEMO]
OPTIONS:
    -h, --help            Print this message.
    -a, --addresses STR   The name of the address file, each address of a separate line, or a binary
                          file previosly created with --save-bin. Binary files are faster to read.
        --save-bin STR    The name of the binary file to write, 20 bytes per address. This is in order
                          to accelerate loading of addresses.
    -p, --path STR        Use this derivation path template, e.g. m/44'/60'/0-99'/0/0-99
                          The default is m/44'/coin'/0-9'/0-1/0-9 for p2pkh addresses and ethereum,
                          m/49'/coin'/0-9'/0-1/0-9 for p2sh addresses,
                          m/84'/coin'/0-9'/0-1/0-9 for bech32 addresses.
        --pp FILE         Read derivation paths from the file, one per line. -p and --pp are mutually exclusive.
    -v, --verbose         Print debug messages.
    -t, --type STR        Address type, one of P2SH, P2PKH_UNCOMPRESSED, P2PKH, bech32, ethereum, solana, ton
                          By default, address type is detected from the address file, if it's text.
                          This options is required when using binary data.
        --tt STR,STR,...  Comma-separated list of address types to search for in the -t HEX mode.
                          When -t HEX, the address file contains hexadecimal 160-bit hashes instead of addresses.
                          Possible values are:
                              P2PKH: rmd160(sha256(der-encoded compressed pubkey))
                              P2PKH_UNCOMPRESSED: rmd160(sha256(der-encoded uncompressed pubkey))
                              P2SH: rmd160(sha256(\x00\x14 . rmd160(sha256(der-encoded compressed pubkey))))
                              ETHEREUM: keccak(64-byte pubkey, x.y in big-endian), used also by Tron.
                          Default: check all hash functions.
    -S, --save FILE       Save found results to the file.
    -m, --mnemo FILE      Read mnemonics from the file, one per line. -m stdin to read from the input pipe.
        --alphabet FILE   Generate mnemonics as passwords from the characters of the given file.
                          Not compatible with --mnemo option.
        --bits INT        Generate mnemonics using RNG of the libbitcoin explorer 3.2.0. The integer number is the entropy length:
                          64 - 6 words, 96 - 9 words, 128 - 12 words, 160 - 15 words, 192 - 18 words, 224 - 21 words
                          256 - 24 words.
    -e, --entropy FILE    Read entropy from the file in hex, one per line. If FILE is 'stdin', read from input pipe.
    -l, --lang STR        Language of the mnemonics generated with --bits, one of en, es, es-nfkd, ja, ja-nfkd, it, fr, cs, ru, uk, zh_Hans, zh_Hant, po, ko, tu.
                          Default is English.
        --start STR       For generated mnemonics, start from this mnemonic.
    -d, --devices STR     Comma-separated list of device indexes (indeces start with 0). By default,
                          run on all devices.
        --bloom NUM       Bloom filter size in GPU, in bytes. Can use K, M, and G suffixes. Default
                          is 1024M.
        --kernel NUL      GPU memory reserved for kernel execution, in bytes. Can use K, M, and G suffixes.
                          Default depends on the device.
        --ec-threads NUM  Number of threads for elliptic curve computations. Default is 128. Should be a multiplier of 32.
                          Set to 64 if you are experiencing out of memory errors.
    -w, --words FILE      Use custom dictionary for '*' placeholders in the mnemo template; each word in a separate text line.
                          Each word should be a valid BIP39 word in the specified language (--lang).
        --dump            Dumps valid mnemonics.
    -r, --random          Randomize the mnemonics generated with MNEMO templates (see below).
        --depth NUM       Depth of the random generator to start with. Default is 0 - start generating entoropy right after
                          the random generator is initialized.
        --core FILE       Read BIP39 seed from the file, one per line. If FILE is 'stdin', read from input pipe.
        --hmac FILE       Read passwords from the file, one per line, and use them as HMAC keys to generate BIP39 seeds.
        --hmac1 FILE      Same as --hmac but doesn't check intermediate iterations.
        --iterations NUM  In the --hmac mode: number of hmac iterations to perform.
        --pass FILE       Read passphrases from the file, one per line.
        --electrum                 Use Electrum's non-standard BIP39 implementation.
        --legacy-electrum Use Electrum's old mnemonic scheme. Only paths in the form of m/0-9/N are accepted.
    MNEMO                 Mnemonic template, up to 24 words. Can contain placeholders '*'. If less than
                          12 words, the rest are placeholders. Each '*' is replaced with one of 2048 words (or one of the words
                          from the dictionary specified with --words option).

Example:
   > bip39scan -a addresses.txt -p m/0'/0-1 -m mnemo.txt
   > bip39scan -a addresses.txt -p m/0'/0-1 --alphabet characters.txt --start kaaaaaaa

 
## Building on Windows VS-2022
Install cmake 3.30+ from this link: https://github.com/Kitware/CMake/releases/download/v3.31.8/cmake-3.31.8-windows-x86_64.msi
Or find another version on this page: https://cmake.org/download/

Install Visual Studio 2022 community: https://learn.microsoft.com/en-us/visualstudio/install/install-visual-studio?view=vs-2022
click the big Download button
 
Install Nvidia CUDA 12.9: https://developer.nvidia.com/cuda-downloads?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local
choose Windows version
 
Install OpenSSL from https://slproweb.com/download/Win64OpenSSL-3_6_0.exe

Go to the "Sources" folder
In cmd run: 

cmake bip39scan

<img width="979" height="556" alt="Image" src="https://github.com/user-attachments/assets/584e0fc1-3ad5-49ef-8498-dca4a3f03538" />

The project files will appear in the folder:
bip39scan.sln <- run this file the project will open
bip39scan.vcxproj
bip39scan.vcxproj.filters
..

<img width="987" height="750" alt="Image" src="https://github.com/user-attachments/assets/4e7d7095-3842-4538-b1d4-2d6e9f2ebc43" />

OpenSSL should be found. If now, rename c:\program files\OpenSSL-Win64 to OpenSSL and re-run.
Note that the libcrypto dll should
be in PATH or in the current directory when running bip39scan.

Visual Studio 2022 opens. In the top toolbar choose: Release/x64.
In the "Solution explorer" to the right, right-click bip39scan, choose "build".
The executable builds in the your-build-directory\Release
 
<img width="1303" height="1039" alt="Image" src="https://github.com/user-attachments/assets/b2dcf48f-37e4-4e8d-89f6-f9892f571bc9" />

If necessary run precomp.exe file precomp.bin will be generated

## Building on Ubuntu:

Below is detailed instruction with bash commands required to build bip39scan.
The symbol '$' denotes command prompt.
If your prompt is shown as '#' on your terminal, skip 'sudo'.
For example, instead of

$ sudo sh cuda_12.0.1_525.85.12_linux.run

you should run

sh cuda_12.0.1_525.85.12_linux.run

Let's start.

install CUDA. Download the linux version from the NVIDIA website and run.
Open https://developer.nvidia.com/cuda-12-0-1-download-archive?target_os=Linux
in your browser and choose your system. The following is valid for Ubuntu 18.04.

$ wget https://developer.download.nvidia.com/compute/cuda/12.0.1/local_installers/cuda_12.0.1_525.85.12_linux.run
$ sudo sh cuda_12.0.1_525.85.12_linux.run

Skip the driver installation (deselect the 'driver' checkbox) if you already have it.

To ensure the cuda is installed, run:
$ nvcc --version

It should print information and version of CUDA.
If no nvcc is found, try adding the CUDA bin path to the PATH variable:
$ export PATH=/usr/local/cuda/bin:$PATH

install build-essential:
$ sudo apt-get install build-essential

Check the gcc version:
$ gcc --version

if the version is less than 9, install gcc 9:

$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:jonathonf/gcc
$ sudo apt-get update
$ sudo apt-get install gcc-9
$ sudo apt-get install g++-9
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 10
$ sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-9 10

install libssl:
$ sudo apt-get install libssl-dev
for the client-server version, install boost:
$ sudo apt-get install libboost-all-dev

You will need Boost version at least 1.71. If apt-get does not intall at least 1.71, build Boost from source:
$ wget https://archives.boost.io/release/1.71.0/source/boost_1_71_0.tar.gz
$ tar -xzvf boost_1_71_0.tar.gz
$ cd boost_1_71_0
$ ./bootstrap.sh --prefix=/usr && ./b2 stage threading=multi link=static
$ sudo ./b2 install threading=multi link=static
$ sudo ln -svf detail/sha1.hpp /usr/include/boost/uuid/sha1.hpp

install cmake from here: https://cmake.org/download/ choose Binary distributions, if that does not work - build from source
$ wget https://github.com/Kitware/CMake/releases/download/v3.28.0/cmake-3.28.0-linux-x86_64.tar.gz
$ tar -xzvf cmake-3.28.0-linux-x86_64.tar.gz

unpack the bip39scan source, let's say bip39scan/
make an empty build directory, and run cmake in it e.g.
$ mkdir bip39scan-build
$ cd bip39scan-build

On first make, it will generate precomp.bin file, which may take quite some time. 
If you already have the precomp.bin, copy it to the build directory and comment this line in the ../bip39scan/CMakeLists.txt: add_dependencies(bip39scan precomp-bin) like this:
#add_dependencies(bip39scan precomp-bin)

Save CMakeLists.txt and run cmake:
$ ../cmake-3.28.0-linux-x86_64/bin/cmake ../bip39scan

ex. cmake -S ./bip39scan -B ./bip39scan-build

where ../bip39scan-build is the source code directory
make the project
$ make bip39scan
