# NextFeed
## A project for Seoul National University HCI class (2023-1)

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/dhbryan75"><br /><div><b>김도현</b></div></a><br /><a href="https://github.com/NextFeed/next-feed-front/commits?author=dhbryan75" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/yms1204"><br /><div><b>송유민</b></div></a><br /><a href="https://github.com/NextFeed/next-feed-front/commits?author=yms1204" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/yxxshin"><br /><div><b>신연상</b></div></a><br /><a href="https://github.com/NextFeed/NextFeed_server/commits?author=yxxshin" title="Code">💻</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

## Running our project on your local environment
We recommend you to make a python environment, such as
```properties
conda create -n NextFeed python=3.8
```

Git clone our two repos,
```properties
git clone https://github.com/NextFeed/NextFeed_server.git
git clone https://github.com/NextFeed/next-feed-front.git
```

Run the AI server from `NextFeed_server`. This is our AI server (which is currently CLIP)
You should make a `settings.json` file for Django (including any secret key!)


```properties
cd NextFeed_server/NextFeed
pip install -r requirements.txt
vim settings.json   # Making settings.json file
python manage.py runserver
```

Your `settings.json` file should look like this; write anything for the secret key!
```json
{
  "SECRET_KEY": "YOUR_ARBITRARY_SECRET_KEY"
}
```

Now, you need to run the front-end server from `next-feed-front`. 

```properties
cd next-feed-front
npm install
```

You need to write your Instagram Account info (for crawling)
```properties
cp .env.sample .env
vim .env    # Write your instagram info!
npm run build
```

Your `.env` file would look like this: wrote PORT=3000 for example
```
PORT=3000

INSTAGRAM_ID={your_instagram_id}
INSTAGRAM_PW={your_instagram_password}
```

Now, your front server is running at the background! You could find our project from `localhost:{PORT_NUM}`, http://localhost:3000 for the given example

To terminate the background server, find and kill it.
```properties
ps -ef | grep node      # Find your background server PID number (will look like node ./server)
kill -9 {PID_NUMBER}
```




