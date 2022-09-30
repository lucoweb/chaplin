# Chaplin
An example movie catalog with Drupal 9 built using DDEV.

# Prerequisites
1. Windows users:
   1. WSL2
   2. Docker
   3. Ubuntu for Windows
   4. [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701?hl=en-us&gl=us) recommended.
2. Linux/Mac OS
   1. Docker
*Please note:* This setup was not tested in either Linux or Mac OS. YMMV.

# Usage
- Clean installation strongly advised.
- Import the DB dump provided and include the images in:
  - sites/default/files/actors
  - sites/default/files/movies
- Import the config sync files from **sites/default/files/sync**.
- Unpack the custom theme Theater and place it in **themes/custom**.
