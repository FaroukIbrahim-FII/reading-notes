# Cryptography (Optional Read)

## Encryption, decryption, and cracking

Encrypting a message
Imagine Caesar wants to send this message:
SECRET MEETING AT THE PALACE
Here's what that might look like encrypted:
YKIXKZ SKKZOTM GZ ZNK VGRGIK
That looks an awfully lot like gobbledygook at first, but this encrypted message is actually very related to the original text.
The Caesar Cipher is a simple substitution cipher which replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount.

### Decrypting a message

According to historical records, Caesar always used a shift of 3. As long as his message recipient knew the shift amount, it was trivial for them to decode the message.
Imagine Caesar sends this message to a comrade:

    EHZDUH EUXWXV

They can then decode the message with certainty. The first letter "E" was shifted by 3 from "B", the second letter "H" was shifted by 3 from "E", etc. The result is this ominous message:

    BEWARE BRUTUS

Check your understanding
Here's another message Caesar might send:

    FURVV WKH UXELFRQ

![encrypt](https://lh3.googleusercontent.com/proxy/JjoWqDu5pzWJp-wE41_Xt6ChWxKnySVFLVlIcSRKP3F_ktJUvdVhnoKcHH-mctoR1OzjhNHEQbMkKYbSv1anGKRxygG74a6bwatox9Du6Ve-8nk5pYzTXM43F5aBzLSjnPUk3sM0ZBOgyAHgxgbS)

### Cracking the cipher

Imagine that a very literate and savvy enemy intercepts one of Caesar's messages.

    RZ VMZ WMDIBDIB VGG AJMXZN OJ EJDI RDOC XGZJKVOMV OJ YZAZVO OCZ ZIZHT LPZZI VO OCZ IDGZ YZGOV

That enemy does not know that Caesar always uses a shift of 3, so he must attempt to "crack" the cipher without knowing the shift.

### Frequency analysis

Human languages tend to use some letters more than others. For example, "E" is the most popular letter in the English language. We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.

### Encryption, decryption, and cracking

Thanks to this exploration of the Caesar Cipher, we now understand the three key aspects of data encryption:

* Encryption: scrambling the data according to a secret key (in this case, the alphabet shift).
* Decryption: recovering the original data from scrambled data by using the secret key.
* Code cracking: uncovering the original data without knowing the secret, by using a variety of clever techniques.
