# Kii-U-Generator

This is my take, a Python implementation, of the Wii U title-key generating algorithm that recently surfaced online.
</br>Title keys are a pbkdf2 hash with sha1 base. A md5 hash of a 'secret' with the title id, minus the prefixed 00 padding, appended to it is used as salt. <br />It needs to be hashed with 20 iterations to produce the correct title key.

## Usage:
Get all the nessessary with the "Download ZIP" button in the Code section.

### Setup
This tool requires either the pycrypto or pycryptodome library. It is recommended to use pycryptodome since it is still maintained.
</br>Use pip to install pycryptodome

First, open the ckey.json file and enter the common key as plaintext. This is a json file so keep the structure as is.

### Ways to Use
Then there are multiple ways to use this tool.
</br>**1:** You can use the included GUI by running gui.py.
</br>**2:** You can use this as a CLI tool. Run keygen.py <title_id> [password].
The password argument is optional and will default to mypass if it's not included. This seems correct for all games that it has been tested on. System titles, however, require a different password. The password is used as part of the generation algorithm for producing the pbkdf2 hash.
</br>**3:** You can include keygen.py in your Python script and use as a library. Please read the source to see the functions available.
