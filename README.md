# YouTube-Scraping-python

Scraping Youtube id, url, and youtube comment from videos

Tools :

- Python
- Selenium

# =======================================

# **INISIALISASI DAN IMPORT MODULE**

```python
!python --version
```

    Python 3.12.3

```python
!apt-get update
```

    'apt-get' is not recognized as an internal or external command,
    operable program or batch file.

```python
!pip install selenium
!pip install bs4
!apt install chromium-chromedriver
```

    Collecting selenium
      Downloading selenium-4.27.1-py3-none-any.whl.metadata (7.1 kB)
    Collecting urllib3<3,>=1.26 (from urllib3[socks]<3,>=1.26->selenium)
      Downloading urllib3-2.3.0-py3-none-any.whl.metadata (6.5 kB)
    Collecting trio~=0.17 (from selenium)
      Downloading trio-0.27.0-py3-none-any.whl.metadata (8.6 kB)
    Collecting trio-websocket~=0.9 (from selenium)
      Downloading trio_websocket-0.11.1-py3-none-any.whl.metadata (4.7 kB)
    Collecting certifi>=2021.10.8 (from selenium)
      Downloading certifi-2024.12.14-py3-none-any.whl.metadata (2.3 kB)
    Collecting typing_extensions~=4.9 (from selenium)
      Downloading typing_extensions-4.12.2-py3-none-any.whl.metadata (3.0 kB)
    Collecting websocket-client~=1.8 (from selenium)
      Downloading websocket_client-1.8.0-py3-none-any.whl.metadata (8.0 kB)
    Collecting attrs>=23.2.0 (from trio~=0.17->selenium)
      Downloading attrs-24.3.0-py3-none-any.whl.metadata (11 kB)
    Collecting sortedcontainers (from trio~=0.17->selenium)
      Downloading sortedcontainers-2.4.0-py2.py3-none-any.whl.metadata (10 kB)
    Collecting idna (from trio~=0.17->selenium)
      Downloading idna-3.10-py3-none-any.whl.metadata (10 kB)
    Collecting outcome (from trio~=0.17->selenium)
      Downloading outcome-1.3.0.post0-py2.py3-none-any.whl.metadata (2.6 kB)
    Collecting sniffio>=1.3.0 (from trio~=0.17->selenium)
      Downloading sniffio-1.3.1-py3-none-any.whl.metadata (3.9 kB)
    Collecting cffi>=1.14 (from trio~=0.17->selenium)
      Downloading cffi-1.17.1-cp312-cp312-win_amd64.whl.metadata (1.6 kB)
    Collecting wsproto>=0.14 (from trio-websocket~=0.9->selenium)
      Downloading wsproto-1.2.0-py3-none-any.whl.metadata (5.6 kB)
    Collecting pysocks!=1.5.7,<2.0,>=1.5.6 (from urllib3[socks]<3,>=1.26->selenium)
      Downloading PySocks-1.7.1-py3-none-any.whl.metadata (13 kB)
    Collecting pycparser (from cffi>=1.14->trio~=0.17->selenium)
      Downloading pycparser-2.22-py3-none-any.whl.metadata (943 bytes)
    Collecting h11<1,>=0.9.0 (from wsproto>=0.14->trio-websocket~=0.9->selenium)
      Downloading h11-0.14.0-py3-none-any.whl.metadata (8.2 kB)
    Downloading selenium-4.27.1-py3-none-any.whl (9.7 MB)
       ---------------------------------------- 0.0/9.7 MB ? eta -:--:--
       ---- ----------------------------------- 1.0/9.7 MB 5.6 MB/s eta 0:00:02
       ------ --------------------------------- 1.6/9.7 MB 4.4 MB/s eta 0:00:02
       -------------- ------------------------- 3.4/9.7 MB 5.6 MB/s eta 0:00:02
       ------------------ --------------------- 4.5/9.7 MB 5.6 MB/s eta 0:00:01
       ---------------------- ----------------- 5.5/9.7 MB 5.4 MB/s eta 0:00:01
       ------------------------- -------------- 6.3/9.7 MB 5.2 MB/s eta 0:00:01
       ---------------------------- ----------- 6.8/9.7 MB 4.9 MB/s eta 0:00:01
       ------------------------------ --------- 7.3/9.7 MB 4.4 MB/s eta 0:00:01
       ------------------------------- -------- 7.6/9.7 MB 4.2 MB/s eta 0:00:01
       ---------------------------------- ----- 8.4/9.7 MB 4.0 MB/s eta 0:00:01
       ------------------------------------ --- 8.9/9.7 MB 3.9 MB/s eta 0:00:01
       ------------------------------------- -- 9.2/9.7 MB 3.8 MB/s eta 0:00:01
       ---------------------------------------- 9.7/9.7 MB 3.6 MB/s eta 0:00:00
    Downloading certifi-2024.12.14-py3-none-any.whl (164 kB)
    Downloading trio-0.27.0-py3-none-any.whl (481 kB)
    Downloading trio_websocket-0.11.1-py3-none-any.whl (17 kB)
    Downloading typing_extensions-4.12.2-py3-none-any.whl (37 kB)
    Downloading urllib3-2.3.0-py3-none-any.whl (128 kB)
    Downloading websocket_client-1.8.0-py3-none-any.whl (58 kB)
    Downloading attrs-24.3.0-py3-none-any.whl (63 kB)
    Downloading cffi-1.17.1-cp312-cp312-win_amd64.whl (181 kB)
    Downloading PySocks-1.7.1-py3-none-any.whl (16 kB)
    Downloading sniffio-1.3.1-py3-none-any.whl (10 kB)
    Downloading wsproto-1.2.0-py3-none-any.whl (24 kB)
    Downloading idna-3.10-py3-none-any.whl (70 kB)
    Downloading outcome-1.3.0.post0-py2.py3-none-any.whl (10 kB)
    Downloading sortedcontainers-2.4.0-py2.py3-none-any.whl (29 kB)
    Downloading h11-0.14.0-py3-none-any.whl (58 kB)
    Downloading pycparser-2.22-py3-none-any.whl (117 kB)
    Installing collected packages: sortedcontainers, websocket-client, urllib3, typing_extensions, sniffio, pysocks, pycparser, idna, h11, certifi, attrs, wsproto, outcome, cffi, trio, trio-websocket, selenium
    Successfully installed attrs-24.3.0 certifi-2024.12.14 cffi-1.17.1 h11-0.14.0 idna-3.10 outcome-1.3.0.post0 pycparser-2.22 pysocks-1.7.1 selenium-4.27.1 sniffio-1.3.1 sortedcontainers-2.4.0 trio-0.27.0 trio-websocket-0.11.1 typing_extensions-4.12.2 urllib3-2.3.0 websocket-client-1.8.0 wsproto-1.2.0


    'apt' is not recognized as an internal or external command,
    operable program or batch file.

```python
import pandas as pd
```

```python
import time
from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.chrome.service import Service

def get_driver():
    options = webdriver.ChromeOptions()
    options.add_argument('--headless')
    options.add_argument('--no-sandbox')
    options.add_argument('--disable-dev-shm-usage')
    driver = webdriver.Chrome(options=options)
    return driver
```

```python
driver = get_driver()
```

#**GET LIST YOUTUBE VIDEO**

```python
# Function for get youtube ID
def get_all_youtube_video_ids(search_keyword, num_results=10, scroll_attempts= 5):
    try:
        # Go to YouTube
        driver.get(f'https://www.youtube.com/results?search_query={search_keyword}&sp=CAM%253D')

        driver.maximize_window()

        # Wait for the results to load
        time.sleep(3)

        # List to store video IDs
        count_data = 0
        video_urls = []
        video_ids = []
        video_channels = []
        video_titles = []
        video_times = []
        video_views = []

        # Scroll down to load more results
        scroll_pause_time = 2  # Time to wait after each scroll
        scroll_attempts = scroll_attempts     # Number of scrolls to load more results

        for _ in range(scroll_attempts):
            # Scroll down the page
            driver.execute_script("window.scrollTo(0, document.documentElement.scrollHeight);")
            time.sleep(scroll_pause_time)

        # Locate all video title elements
        video_elements = driver.find_elements(By.XPATH, '//*[@id="dismissible"]')

        # Extract video IDs from each video link
        for video_element in video_elements:
            video_title = video_element.find_element(By.XPATH, '..//*[@id="video-title"]')
            video_url = video_title.get_attribute("href")
            if video_url and 'v=' in video_url:  # Only process valid video URLs
                video_id = video_url.split('v=')[1].split('&')[0]
                video_title = video_title.text

                # Find the video channel
                try:
                    video_channel = video_element.find_element(By.XPATH, '..//*[@id="channel-info"]').text
                except:
                    video_channel = None

                # Find the video publish time (time ago)
                try:
                    video_time = video_element.find_element(By.XPATH, '..//div[@id="metadata-line"]/span[2]').text
                except:
                    video_time = None

                # Find the view count
                try:
                    view_count = video_element.find_element(By.XPATH, '..//*[@id="metadata-line"]/span[1]').text
                except:
                    view_count = None

                # Append to the lists
                video_urls.append(f"https://www.youtube.com/watch?v={video_id}")
                video_ids.append(video_id)
                video_channels.append(video_channel)
                video_titles.append(video_title)
                video_times.append(video_time)
                video_views.append(view_count)


            # Stop if we've collected enough video IDs
            if len(video_ids) >= num_results:
                break

        print("getting data :", len(video_ids))
        # Return the list of video IDs
        return video_urls, video_ids, video_channels, video_titles, video_times, video_views

    finally:
        # Close the browser after scraping is done
        print("Completed")
        # driver.quit()
```

```python
search_keyword = "indonesia"
num_results = 500
scroll_attempts = 10
video_urls, video_ids, video_channels, video_titles, video_times, video_views = get_all_youtube_video_ids(search_keyword, num_results, scroll_attempts)

video_list = pd.DataFrame({
    'Video URL': video_urls,
    'Video ID': video_ids,
    'Video Channel': video_channels,
    'Video Title': video_titles,
    'Release Time': video_times,
    'Views': video_views
})
```

    getting data : 71
    Completed

```python
video_list
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Video URL</th>
      <th>Video ID</th>
      <th>Video Channel</th>
      <th>Video Title</th>
      <th>Release Time</th>
      <th>Views</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>https://www.youtube.com/watch?v=cx4Xwae513g</td>
      <td>cx4Xwae513g</td>
      <td>Unisys Music</td>
      <td>Force 2016 Full Movie | John Abraham | Vidyut ...</td>
      <td>10 years ago</td>
      <td>143M views</td>
    </tr>
    <tr>
      <th>1</th>
      <td>https://www.youtube.com/watch?v=yNKvkPJl-tg</td>
      <td>yNKvkPJl-tg</td>
      <td>tvOneNews</td>
      <td>Live Streaming tvOne 24 Jam</td>
      <td>None</td>
      <td>2.6K watching</td>
    </tr>
    <tr>
      <th>2</th>
      <td>https://www.youtube.com/watch?v=uBIjpx2Re3M</td>
      <td>uBIjpx2Re3M</td>
      <td>Jason Vlogs Indonesia</td>
      <td>Jason and the fun cop adventure Children's sto...</td>
      <td>3 years ago</td>
      <td>72M views</td>
    </tr>
    <tr>
      <th>3</th>
      <td>https://www.youtube.com/watch?v=aKtb7Y3qOck</td>
      <td>aKtb7Y3qOck</td>
      <td>Alffy Rev</td>
      <td>“Wonderland Indonesia” by Alffy Rev ft. Novia ...</td>
      <td>3 years ago</td>
      <td>62M views</td>
    </tr>
    <tr>
      <th>4</th>
      <td>https://www.youtube.com/watch?v=DOOrIxw5xOw</td>
      <td>DOOrIxw5xOw</td>
      <td>KOMPASTV</td>
      <td>LIVE STREAMING 24 JAM KOMPASTV</td>
      <td>None</td>
      <td>2.6K watching</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>66</th>
      <td>https://www.youtube.com/watch?v=_zdcJQ-e0h0</td>
      <td>_zdcJQ-e0h0</td>
      <td>Bing - Bahasa Indonesia</td>
      <td>Bing menyukai Arlo si kucing! | Bing Bahasa In...</td>
      <td>1 year ago</td>
      <td>2.6M views</td>
    </tr>
    <tr>
      <th>67</th>
      <td>https://www.youtube.com/watch?v=2uzwHZ6PK4Q</td>
      <td>2uzwHZ6PK4Q</td>
      <td>Araya Vlogs</td>
      <td>This City WILL DISAPPEAR Under WATER: JAKARTA ...</td>
      <td>4 months ago</td>
      <td>2.6M views</td>
    </tr>
    <tr>
      <th>68</th>
      <td>https://www.youtube.com/watch?v=_Rt8zW0IanY</td>
      <td>_Rt8zW0IanY</td>
      <td>RCTI Sports</td>
      <td>AFC U23 ASIAN CUP QATAR 2024 - QUARTER FINAL I...</td>
      <td>7 months ago</td>
      <td>2.5M views</td>
    </tr>
    <tr>
      <th>69</th>
      <td>https://www.youtube.com/watch?v=GbUmyFTJreA</td>
      <td>GbUmyFTJreA</td>
      <td>AFC Asian Cup</td>
      <td>Full Match | AFC Asian Qualifiers™️ Road To 26...</td>
      <td>Streamed 3 months ago</td>
      <td>2.5M views</td>
    </tr>
    <tr>
      <th>70</th>
      <td>https://www.youtube.com/watch?v=fE7bLyVB9xk</td>
      <td>fE7bLyVB9xk</td>
      <td>Indonesian Idol 2025</td>
      <td>Alasan Rafi Wiratama Ikut Indonesian Idol | Au...</td>
      <td>2 weeks ago</td>
      <td>2.4M views</td>
    </tr>
  </tbody>
</table>
<p>71 rows × 6 columns</p>
</div>

```python
video_list.to_csv('video_list.csv', index=False, encoding='utf-8')
```

# **GET COMMENTS DATASET**

```python
def getCommentsData(video_ID):
  driver.get(f'https://www.youtube.com/watch?v={video_ID}')
#   driver.get(video_ID)
  # Initialize WebDriver using Chrome Browser
  driver.maximize_window()

  # Scroll down to load comments
  for _ in range(10):
      driver.execute_script("window.scrollTo(0, document.documentElement.scrollHeight);")
      time.sleep(2)

  # Wait for the comments section to load
  comments_section = WebDriverWait(driver, 10).until(
      EC.presence_of_element_located((By.XPATH, "/html/body/ytd-app/div[1]/ytd-page-manager/ytd-watch-flexy/div[5]/div[1]/div/div[2]/ytd-comments/ytd-item-section-renderer/div[3]"))
  )

  # for the video author section to load
  author_section = driver.find_element(By.XPATH, "/html/body/ytd-app/div[1]/ytd-page-manager/ytd-watch-flexy/div[5]/div[1]/div/div[2]/ytd-watch-metadata/div/div[2]/div[1]/ytd-video-owner-renderer/div[1]/ytd-channel-name/div/div/yt-formatted-string")

  # Extract the HTML content of the section
  comments_html = comments_section.get_attribute('innerHTML')
  author_html = author_section.get_attribute('innerHTML')

  # Parse the HTML content with BeautifulSoup
  soup = BeautifulSoup(comments_html, 'html.parser')
  soup_author = BeautifulSoup(author_html, 'html.parser')

  # Extract the text
  comments = [comment.text for comment in soup.find_all('yt-attributed-string', {'class': 'style-scope ytd-comment-view-model'})][0::2]
  usernames = [username.text.strip() for username in soup.find_all('span', {'class': 'style-scope ytd-comment-view-model style-scope ytd-comment-view-model'})]
  author = [author.text.strip() for author in soup_author.find_all('a', {'class': 'yt-simple-endpoint style-scope yt-formatted-string'})]

  channels = [author[0]] * len(comments) if len(comments) > 0 else [author[0]]

  print(f"Getting Comments : {len(comments)} Comments, from : {author[0]}")
  return comments, usernames, channels
```

```python
# run driver
driver = get_driver()
```

```python
# input video ID
video_url = 'fE7bLyVB9xk'

comments, usernames, channels = getCommentsData(video_url)
```

    Getting Comments : 160 Comments, from : Indonesian Idol 2025

```python
comments_dataset = pd.DataFrame({
    'Username': usernames,
    'Comment': comments
})

comments_dataset
```

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }

</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Username</th>
      <th>Comment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>@rafiadityawiratama5315</td>
      <td>Terima kasih semuanya, Atas dukungan serta apr...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>@rickyfe1055</td>
      <td>Salah satu kontestan yg bakal lolos masuk spek...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>@HeraldGaming90</td>
      <td>Tapi gw seneng sih sama Pak Anang, ada makna t...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>@akbarfadillah4929</td>
      <td>Semangat pejuang semester akhir, gak mudah kul...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>@dennissitompul1901</td>
      <td>Damn ! suaranya magic banget, berkarakter, mar...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>155</th>
      <td>@InfoDite27</td>
      <td>Asli kerennn.. joshhh</td>
    </tr>
    <tr>
      <th>156</th>
      <td>@dodiprananda</td>
      <td>auto jadi jagoan gue untuk musim ini. Selamat ...</td>
    </tr>
    <tr>
      <th>157</th>
      <td>@ikakurniawati9150</td>
      <td>Menyaalaaaa Rafiiiiiiiii.. Doa Mamamu dan org2...</td>
    </tr>
    <tr>
      <th>158</th>
      <td>@fadiaainun</td>
      <td>Enakkk pwol suaranya, it's goes to top 5</td>
    </tr>
    <tr>
      <th>159</th>
      <td>@DeviAfrida</td>
      <td>ENAK BANGET SUARA LU BANG</td>
    </tr>
  </tbody>
</table>
<p>160 rows × 2 columns</p>
</div>

```python
comments_dataset.to_csv('Comments_Dataset.csv', index=True, encoding='utf-8')
```
