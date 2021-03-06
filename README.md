# Spiderboi
[![NPM](https://nodei.co/npm/spiderboi.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/spiderboi/)

A web crawling library written in TypeScript.

# Example
```typescript
import Crawler from 'spiderboi';

async function run() {
    const crawler = new Crawler('https://google.com');

    // this gets the site's robots.txt so that the crawler can respect it
    await crawler.readyUp();

    const out = await crawler.crawl('/search/about');
    console.log(out);
}

run();
/**
 * above code should output:
 * [ 'https://google.com/search/about/',
 * 'https://google.com/search/about/',
 * 'https://google.com/#app-store',
 * 'https://google.com/#app-store',
 * 'https://google.com/#image-texts' ]
 * 
 * unless of course google changes the /search/about page and ruins this example.
 */
```