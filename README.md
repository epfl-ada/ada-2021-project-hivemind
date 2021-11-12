# Title

<!-- TABLE OF CONTENTS -->
<h2 id="table-of-contents"> :book: Table of Contents</h2>

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#abstract"> ➤ Abstract</a></li>
    <li><a href="#additional-datasets"> ➤ Additional datasets</a>
        <ul>
            <li><a href="#additional-datasets-speaker-attributes">Speaker attributes</a></li>
            <li><a href="#additional-datasets-disasters">Disasters</a></li>
            <li><a href="#additional-datasets-wdi">World development indicators</a></li>
            <li><a href="#additional-datasets-gdelt">GDELT geographic lookup of domains</a></li>
        </ul>  
    </li>
    <li><a href="#folder-structure"> ➤ Folder Structure</a></li>
    <li><a href="#timeline"> ➤ Proposed timeline</a></li>
    <li><a href="#organization"> ➤ Organization within the team</a></li>
    <li><a href="#questions-for-tas"> ➤ Questions for TAs</a></li>
  </ol>
</details>

<!-- ABSTRACT -->
<h2 id="abstract"> :pencil: Abstract</h2>

TODO: A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?
Research Questions: A list of research questions you would like to address during the project.


<!-- ADDITIONAL DATASETS -->
<h2 id="additional-datasets"> :floppy_disk: Additional datasets</h2>

TODO: List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.

<!-- ADDITIONAL DATASETS SPEAKER ATTRIBUTES -->
<h3 id="additional-datasets-speaker-attributes">   Speaker attributes</h3>

This dataset helps us to find connection between the speaker and the quotation when it is about a disaster. We can observe if the speaker is from the same country as the place of the disaster, or she/he is a scientist, expert talking about the event.

Data source: Wikidata

<!-- ADDITIONAL DATASETS DISASTERS -->
<h3 id="additional-datasets-disasters">   Disasters</h2>

In this dataset, we managed to get the most important attributes of the natural disasters in this century. In our analysis, we want to find connection between the attributes of the disasters and the length and distribution of time they talk about the disaster. Just to enumerate probably the most important factors, we get the type, the location the date, casualities and reconstruction cost. Also, one can find some disaster type specific attributes, for example the magnitude of a earthquake.

Data source: https://public.emdat.be/data

<!-- WORDL DEVELOPMENT INDICATORS -->
<h3 id="additional-datasets-wdi">   World development indicators</h2>

One important factor in how much the people talk about a disaster might be the country and its attributes. In  this dataset, the most important development indicators of the country can be found, for example GDP, population, fertility rate, and life expectancy at birth. We would like to observe whether there is a connection between these indicators and the length and distribution of time they talk about the disaster. 

Data source: https://databank.worldbank.org/source/world-development-indicators

<!-- WORDL DEVELOPMENT GDELT -->
<h3 id="additional-datasets-gdelt">   GDELT geographic lookup of domains</h2>

The geographical location of newspapers could affect the citations contained in them. Although the quotes in the Quotebank dataset contain links to the article in which they were found, we cannot find out the true geographical location of the news source from the link itself. E.g. theguardian.com and nytimes.com both use .com TLD, but they are reporting events in different countries. That's why we decided to choose a GDELT dataset that associates a particular domain with the right country from which that news source comes. 

Data source: https://blog.gdeltproject.org/mapping-the-media-a-geographic-lookup-of-gdelts-sources/

<!-- :paw_prints:-->
<!-- FOLDER STRUCTURE -->
<h2 id="folder-structure"> :cactus: Folder Structure</h2>

    .
    │
    ├── datasets
    │   ├── quotebank
    │   │   └── quotes-{year}.parquet
    │   │
    │   ├── gdelt_domains_by_country
    │   │   ├── gdeltdomainsbycountry_may2018.txt
    │   │   └── FIPS_country.txt
    │   │
    │   ├── emdat
    │   │    └── emdat_public_2021_11_06.csv
    │   │
    │   └── wdi
    │       ├── databank_wdi_data.csv
    │       └── databank_wdi_metadata.csv
    │
    ├── quotes_eda.ipynb
    ├── wdi_eda.ipynb  
    ├── disasters_eda.ipynb    
 
<!-- METHODS -->
<h2 id="methods"> :mag: Methods</h2>

TODO: 

<!-- PROPOSED TIMELINE -->
<h2 id="timeline"> :calendar: Proposed timeline</h2>

TODO: 
1. Project idea clarification
2. Additional data collection and processing
3. Data statistical analysis

<!-- PROPOSED TIMELINE -->
<h2 id="organization"> :dart: Organization within the team</h2>

TODO: A list of internal milestones up until project Milestone 3.

<!-- QUESTIONS FOR TAs -->
<h2 id="questions-for-tas"> :question: Questions for TAs (optional)</h2>

Add here any questions you have for us related to the proposed project.
