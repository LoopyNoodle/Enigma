# Enigma

This code simulates the working of an **Enigma Machine** that was used during World War II. The Enigma is a cipher device that uses a combination of rotors, a reflector, and a Steckerbrett (plugboard) to encrypt and decrypt messages. Key components of the Enigma include:
- **Steckerbrett** that allows specific letters to be swapped before and after encryption; the letter swap is defined by a list of letter pairs. If a letter is part of a pair, it gets swapped; otherwise, it remains unchanged.
- **Rotors** that apply a Caesar cipher-like shift to the letters based on their current position. Each rotor has a **notch** position, and when the rotor reaches this position, it triggers the next rotor to rotate. The rotors rotate after each letter is encoded, ensuring that the cipher becomes more complex with each keypress.
- **Reflector** is a static wiring configuration that takes the letter after it passes through all rotors and sends it back through the rotors in the reverse order, making the encryption process symmetric and adding another layer of complexity.

### Encryption Process

1. The input letter passes through the Steckerbrett, swapping with a configured pair if applicable.
2. The letter then passes through the rotors from right to left, with each rotor applying a cipher shift based on its current position.
3. The letter is reflected by the reflector.
4. The letter then passes back through the rotors from left to right, undoing the cipher shifts applied by the rotors.
5. Finally, the letter passes through the Steckerbrett again to swap it back to its original position.

After each letter is encrypted, the rotors rotate, changing their configuration for the next encryption.

### Decryption Process

The decryption process uses the same steps as encryption due to the symmetry of the Enigma machine. However, to decrypt a message, the rotors must be reset to their initial positions.

### Usage

1. **Encryption**:  
   Enter the message you want to encrypt, and the machine will produce an encrypted string.
   
   ```python
   message = input('Enter your message:')
   enc = enigma.encrypt(message) # encrypted message
   print("Encrypted:", enc)
   ```

2. **Decryption**:  
   The encrypted message can be decrypted by passing it back through the same machine, as long as the rotor settings are the same as when it was encrypted.

   ```python
   dec = enigma.decrypt(enc) # decrypted message
   print("Decrypted:", dec)
   ```
