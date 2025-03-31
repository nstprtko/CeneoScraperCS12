# CeneoScraperCS12
https://www.ceneo.pl/17230358#tab=reviews

## Algorithm for extracting opinions about single product from Ceneo.pl

1. Send the request for accesing first webpage with opinions about product 
2. if response is ok, parse HTML page content into DOM structure 
3. Extract form DOM structure opinions and their components
4. Save opinion with their components to complex data structure 
5. If there are more pages with opinions, repeat steps 1-5 
6. Save data strucutres with opinions into database

## Structure of single opinion on Ceneo.pl
|Component|Variable|Selector|
|---------|--------|--------|
|opinion|opinion|div.js_product-review:not(.user-post--highlight)|
|opinion ID|opinion_id|["data-entry-id"]|
|opinion’s author|author|span.user-post__author-name|
|author’s recommendation|recommend|span.user-post_author-recomendation > em|
|score expressed in number of stars|stars|span.user-post_score-count|
|opinion’s content|content|div.user-post_text|
|list of product advantages|pros|div.review-feature__item--positive|
|list of product disadvantages|cons|div.review-feature__item--negative|
|how many users think that opinion was helpful|up_votes|button.vote-yes["data-total-vote"]|
|how many users think that opinion was unhelpful|down_votes|button.vote-no["data-total-vote"]|
|publishing date|published|span.user-post__published > time:nth-child(1)["datetime"]|
|purchase date|purchased|span.user-post__published > time:nth-child(2)["datetime"]|