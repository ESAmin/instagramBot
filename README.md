# Instagram Bot
## Bot
### Followers

* hello
* whats up
- ygjygyj
    * ukfdhdukh

[google](http://google.com)
<br>
![google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png)

```python 
from instabot import Bot
import requests
import os
import sys

bot = Bot()
bot.login(username='YourUsername', password='YourPassword')

target_username = sys.argv[1]
target_path = './' + target_username
if not os.path.isdir(target_path):
    print(target_path)
    os.makedirs(target_path)

target_user_id = bot.get_user_id_from_username(target_username)
stories = bot.get_user_stories(target_user_id)[1]

for story in stories:
    filename = story.split('/')[-1].split('?')[0]
    story_request = requests.get(story)
    open( target_path + '/' + filename, 'wb').write(story_request.content)
```
**bold**

*italic*
