# data-512-homework_2

## Documentation

This repository contains the necessary notebooks and files required for homework 2. The goal of this assignment is to retrieve politician Wikipedia pages from the Pageview API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end), [data license](https://dumps.wikimedia.org/legal.html)) using the Wikimedia REST API ([website](https://www.mediawiki.org/wiki/Wikimedia_REST_API), [terms of use](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)). Next, using the ORES ([website](https://www.mediawiki.org/wiki/ORES), [API](https://www.mediawiki.org/wiki/API:Info)) or “Objective Revision Evaluation Service” a machine learning system that estimates Wikipedia article quality. Then, after retrieving the data and estimating article quality, create data tables showing the countries with the most and least total articles per capita, countries with the most and least high-quality articles per capita, and sorting the regions by article quality per capita and high-quality article population per capita.

The files required from step 1 of the homework are in the root folder of the repository. Steps 2 and 3 of the homework were completed using retrieve_and_combine_data.ipynb with the outputs being stored in the data folder. The notebook has all libraries declared in the first cell. The file that contains the names of politicians I was unable to retrieve article quality scores for is named no_ORES_score_list.csv. The list of countries that were not in the politicians_by_country_SEPT.2022.csv file is named wp_countries-no_match.txt. The consolidated data is stored in wp_politicians_by_country.csv and the schema of the file is in the table below:


| Columns | Data Type |
| --- | --- | 
| country | string |
| region | string |
| population | float |
| article_title | string |
| revision_id | int |
| article_quality | string |

Steps 4 and 5 of the homework were completed using analysis.ipynb. The notebook has all libraries declared in the first cell. This notebook output no files, but the required data tables can be found within the notebook’s analysis.

## Research Implications

The first thing I found in the data was something I expected, that India and China were in the bottom 10 of politician articles per capita. I was also not surprised to find that the nations in the top 10 of articles per population had small populations (all were under one million!). I had both of these assumptions because I thought larger population countries would not have a proportionally large number of politician pages to keep up with the total. I also assumed that small population countries would have the inverse occur and they did. While this cursory view of the data agreed with my assumptions further analysis is required to see if politicians increase at a proportional rate with population, and if they do why so many politicians are missing in Wikipedia for larger countries.

One bias I came into the analysis that was incorrect was the high proportion of high-quality of articles for the Caribbean and Central American region. I assumed that English Wikipedia would have the most high-quality articles per capita for European regions due to their proximity as well as intertwined politics (NATO and EU) to multiple English-speaking countries. While the Caribbean and Central American regions also have that proximity to English-speaking countries, the regions do not have the same level of political relationships (excluding Mexico with the USMCA). However, the Caribbean region had the second most high-quality articles per capita behind only Southern Europe, and Central America is the only other region that has close to the same number of high-quality articles to European regions.

Findings about individual countries that that surprised me were China, Italy, and Turkey not having a single high-quality article for their politicians. For China, since it has the largest population of any nation, I assumed its politician’s Wikipedia pages would at least have one high-quality article. As for Italy and Turkey, their relationships to English speaking nations, Italy in the EU and Turkey in NATO, as well as larger populations made it surprising to see that they did not have a single high-quality article either. One additional note about China, its large size along with lack of high-quality articles is the main cause for East Asia being the region with the lowest number of high-quality articles per capita.

### What biases did you expect to find in the data (before you started working with it), and why?

I expected India and China to do poorly with articles per capita due to their size and distance from English speaking nations, as well as European nations to rank highly with articles per capita and high-quality articles per capita because of the proximity and political ties to English speaking nations.

### What might your results suggest about (English) Wikipedia as a data source?

English Wikipedia as a source becomes less reliable the less English-speaking people would interact or know of the topic. It appears that interest from English speakers is an important factor for an article to become high-quality.

### What might your results suggest about the internet and global society in general?

These results suggest that the information on the internet is disproportionately created for English speakers. There may be fewer resources as well as unreliable resources for non-English speaking communities or topics of interest.
