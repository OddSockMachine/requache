# Requache = requests + cache

I do a lot of work scraping web content. This little function helps with two things: speed and manners.

1) Even if you optimize your scraping app well (using worker pools, concurrency, callbacks etc), you're still going to be limited by your network or the target server's speed.

2) If your processing of the data isn't right first time, you'll run again, and pull a bunch of data from their site. That's not cool, and in some cases will get you blocked.

To get around these two limitations, we simply cache the text returned by called to requests.

Whenever you'd normally call requests.get(url).text instead call requache.get(url). The first time you run your scraping app, everything works as usual. Second time round, everything's super fast and the target server is never touched. This means you can perfect your data processing on cached data as if you were running against live data.
