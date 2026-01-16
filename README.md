# Brave Search AI Image Results Blocking Docs
Documentation of blocking AI image results from appearing in Brave Search searches.

## Brave search image URLs
* Image result URL format: `https://imgs.search.brave.com/{hash}/{resize instruction}/{gravity and encoding}/{base 64 encoded with slashes every 16 chars}`
* Format for adding normal rules: `search.brave.com##.image-result:has(img[src^="https://imgs.search.brave.com"][src*="/{base 64 encoded with slashes}"])`
* Format for adding regex rules: `search.brave.com##.image-result:has(img:matches-attr(src="{base 64 encoded with slashes regex}/"))`

## Image result decoding
1. Get the `{base 64 encoded with slashes}` part of the URL
2. Remove the slashes
3. Visit `https://www.base64decode.org`
4. Paste the URL and click "< DECODE >"

## Encoding images URLs for search results
1. Visit `https://www.base64encode.org` 
2. Make sure Base64URL format is enabled
3. Past the URL and click "> ENCODE <"
4. Copy the result
5. Remove the final character (because it changes when the url is longer in search results, due to how base64 works)
6. Insert slashes every 16 chars
