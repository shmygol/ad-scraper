# ad-scraper
Uses Nokogiri to fetch context ads from Google, Bing and Yahoo platforms by the given list of keywords for marketing analysis. Inspired by https://github.com/caser/google-ad-scraper

## Code Example
```
require 'ad_scraper'
time = Time.new
AdScraper::get_parsed_pages(query_list.split(','), ['yahoo', 'google', 'bing']).each do |page|
    puts "==== #{page.type.upcase} = #{page.query.upcase} ===="
    page.ads.each do |ad|
        puts
        puts 'HEADLINE: ' + ad[:headline].upcase
        puts
        puts ad[:node].to_s
    end
end
```
