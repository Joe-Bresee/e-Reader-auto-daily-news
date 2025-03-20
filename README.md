# e-Reader-auto-daily-news
A small project to automate how you can retrieve daily news for free to read every morning on your e-reader while you drink your coffee.

This project automates the process of fetching news articles from various sources and syncing them to Dropbox, specifically for use with a **Kobo** eReader. 

## Requirements:
- Raspberry Pi (or similar Linux-based device) with Desktop environment (CLI requires Cron automation, which can be done but I just used the GUI... reason why below)
- [Calibre](https://calibre-ebook.com/)
- [Maestral](https://maestral.app/) (for Dropbox syncing)
- Dropbox account
- Internet connection
- eReader
- Dropbox compatibility (special set-up for kobo clara)

## Gaining Dropbox Compatibility (**Kobo**)
Some eReaders do not come with out-of-the box Dropbox compatibility. This can be achieved using **KoReader** and **NickelMenu**:
1. Follow this tutorial to download **KoReader** and **NickelMenu**: 'https://www.youtube.com/watch?v=OJ9AIJW-qGI'
2. With your eReader plugged in, navigate to 'KOBOeReader/.adds/nm/config.'
3. add 'menu_item:main:dropbox:nickel_open:library:dropbox'. It doesn't matter where, you can just add it to the very top of the file.
4. With your eReader plugged in, navigate to 'Kobo(E:)/.kobo/Kobo/KoboReader.conf'.
5. Find: 'dropbox_link_account_poll=' and change to 'dropbox_link_account_poll= https://authorize.kobo.com/{region}/{language}/LinkDropbox', change your region and language to what you want.
6. Find: 'kobo_dropbox_link_account_enabled=False' and change to 'kobo_dropbox_link_account_enabled=True'.
7. Restart your eReader.
8. Press on your NickelMenu, press Dropbox, and follow the steps to connect.

## Setup Instructions:

1. **Install Calibre**  
   Instructions for installing Calibre (you can follow their [installation guide](https://calibre-ebook.com/download)).

2. **Install Maestral**  
   Follow Maestral’s installation guide to sync your Dropbox on the Raspberry Pi.

3. **Setup Fetch News in Calibre**  
   - Open Calibre and go to **Fetch News** → **Schedule News Download**.
   - Add your news sources (e.g., National Geographic, Bloomberg, etc.).
   - You can choose when to automatically delete news as well within the fetch news tab.
   - Set the output directory to `~/Dropbox/Apps/'Rakuten Kobo'/News/` by clicking on the down arrow to the right of the stack of books icon on the top menu, and switch/create library and change your library location.
   - Note the GUI must be running in order for the news syncing to work. Otherwise, you must set up cron jobs.

**Usage**
   - In your eReader, go to Dropbox (Via NickelMenu, if required for your device).
   - Navigate to your /News folder.
   - Download wanted articles
   - Happy reading! 
