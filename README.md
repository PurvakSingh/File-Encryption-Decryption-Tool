# File-Encryption-Decryption-Tool

The provided HTML code implements a **secure, client-side file encryption and decryption tool** using modern web technologies such as **React**, **Tailwind CSS**, and the **Web Crypto API**. The core functionality allows users to select a file, enter a password, and either encrypt or decrypt it directly in the browser without uploading any data to a server, ensuring maximum privacy and security.

At the heart of the application is the `App` component, which manages all application states using React hooks. Users can toggle between "Encrypt" and "Decrypt" modes, upload a file, and enter a password. The tool validates the input to ensure a password of at least 8 characters is provided before proceeding.

For encryption, the tool uses the Web Crypto API to derive a secure AES-256-GCM key from the password using **PBKDF2** with a randomly generated 16-byte salt and 100,000 iterations. It also generates a random 12-byte initialization vector (IV). The input file is read as an ArrayBuffer, encrypted using the derived key and IV, and the result is combined with the salt and IV to form a final encrypted blob. This blob is then offered as a downloadable file with a `.encrypted` extension.

Decryption is performed similarly: the tool extracts the salt, IV, and ciphertext from the uploaded encrypted file, regenerates the key using the password and salt, and attempts to decrypt the content using AES-GCM. If successful, the decrypted content is provided for download with an appropriate filename.

The user interface is clean and responsive, styled using Tailwind CSS, and includes real-time feedback such as success or error messages, loading indicators, and graceful handling of incorrect input. All animations and transitions are managed via custom CSS for a smoother user experience.

Overall, this tool effectively demonstrates secure file handling using cryptographic standards, all within the browser. It serves as a practical solution for users who need to encrypt sensitive files without relying on third-party services, reinforcing the principle of zero trust and full user-side control over data security.
