Scraping Google News


# Install scraparazzie and levenshtein
!pip install scraparazzie
!pip install levenshtein

# Import scraparazzie
from scraparazzie import scraparazzie

# Scrape news relevant to battery in USA, set maximum results
client = scraparazzie.NewsClient(language = 'english', location = 'United States', query = 'battery', max_results = 10)

# Save crawling results into items
items = client.export_news()

# Show news obtained
print(len(items))

# Show content in loop
for i, item in enumerate(items):
    print(' No. ' + str(i+1) + ': ')
    print(' Topic: ' + item['title'])
    print(' Source: ' + item['source'])
    print(' Link: ' + item['link'])
    print('Date: ' + item['publish_date'])
    

