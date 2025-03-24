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
|opinion|opinion||
|opinion ID|opinion_id||
|opinion’s author|author||
|author’s recommendation|recommend||
|score expressed in number of stars|stars||
|opinion’s content|content||
|list of product advantages|pros||
|list of product disadvantages|cons||
|how many users think that opinion was helpful|up_votes||
|how many users think that opinion was unhelpful|down_votes||
|publishing date|published||
|purchase date|purchased||