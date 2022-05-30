# Google Image Scraper:
A library to scrape google images

# Installation:
1. Open cmd
2. Clone the repository (or [download](https://github.com/ohyicong/Google-Image-Scraper/archive/refs/heads/master.zip))
    ```
    git clone https://github.com/ohyicong/Google-Image-Scraper
    ```
3. Install Dependencies
    ```
    pip install selenium, requests, pillow
    ```
4. Run the code
    ```
    python main.py
    ```

# Usage:
```python
#Import libraries (Don't change)
from GoogleImageScrapper import GoogleImageScraper
import os
from patch import webdriver_executable

#Define file path (Don't change)
webdriver_path = os.path.normpath(os.path.join(os.getcwd(), 'webdriver', webdriver_executable()))
image_path = os.path.normpath(os.path.join(os.getcwd(), 'photos'))

#Add new search key into array ["cat","t-shirt","apple","orange","pear","fish"]
search_keys= ["cat","t-shirt"]

#Parameters
number_of_images = 10
headless = True
min_resolution=(0,0)
max_resolution=(1920,1080)

#Main program
for search_key in search_keys:
    image_scrapper = GoogleImageScraper(webdriver_path,image_path,search_key,number_of_images,headless,min_resolution,max_resolution)
    image_urls = image_scrapper.find_image_urls()
    image_scrapper.save_images(image_urls)

```
Add the **keywords** you want to scrape images for, in the **search_keys** list (line 31) and the number of images you want for each class in **number_of_images** variable (line 34). All the images belonging to each of the classes in **search_keys** will be saved in **photos** folder inside the directory of this cloned repository.

To use this library run the following command in a command prompt/ terminal inside the directory of this cloned repository:
```
python main.py
```
