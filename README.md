# Natural disasters in quotes

<!-- TABLE OF CONTENTS -->
<h2 id="table-of-contents"> :book: Table of Contents</h2>

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#abstract"> ➤ Abstract</a></li>
    <li><a href="#research-questions"> ➤ Research questions</a></li>
    <li><a href="#additional-datasets"> ➤ Additional datasets</a>
        <ul>
            <!-- <li><a href="#additional-datasets-speaker-attributes">Speaker attributes</a></li> -->
            <li><a href="#additional-datasets-disasters">Disasters</a></li>
            <li><a href="#additional-datasets-wdi">World development indicators</a></li>
            <li><a href="#additional-datasets-gdelt">GDELT geographic lookup of domains</a></li>
        </ul>  
    </li>
    <li><a href="#folder-structure"> ➤ Folder Structure</a></li>
    <li><a href="#methods"> ➤ Methods</a></li>
    <!--<li><a href="#timeline"> ➤ Proposed timeline</a></li>-->
    <li><a href="#organization"> ➤ Organization within the team</a></li>
    <!--<li><a href="#questions-for-tas"> ➤ Questions for TAs</a></li>-->
  </ol>
</details>

<!-- ABSTRACT -->
<h2 id="abstract"> :pencil: Abstract</h2>

Every year, natural disasters happen and often take many lives. After such events, the pages of newspapers are full of quotes from people expressing regret for the unfortunate event. These events often remain in people's memory for a lifetime. What influences how long these events will be talked about? In this research project, our goal is to explore how much is said about the biggest earthquakes after they have occurred and what factors influence this. We will look for answers in the [Quotebank](https://github.com/epfl-dlab/Quotebank) 2008-2020 quotes on disasters taken from the [international disasters database](https://public.emdat.be/data) combined with world development indicators from the [World Data Bank](https://databank.worldbank.org/source/world-development-indicators). To simplify disaster quote detection, we will further look into classifying the quotes by whether they talk about a disaster or not.


<h2 id="research-questions"> :electron: Research questions</h2>
<!-- Research Questions: A list of research questions you would like to address during the project. -->

We proposed to explore two questions in this research project.

First, how correctly will NLP models trained on disaster tweets like in [this kaggle challenge](https://www.kaggle.com/c/nlp-getting-started/overview) generalize to classifying disaster quotes in Quotebank? This question is important in respect of robustness analysis of models and their transfer learning capabilities.

Second, what factors influence how long a earthquake will be talked about in Quotebank quotes from 2008 to 2020? The interesting factors include total deaths, total damage in dollars, country of disaster, wealth indicators of the country, etc. 
<!-- So, we analyse this question from the point of the disaster specific traits of the event, and from the location of the event. -->

<!-- There are various other research question related to this that are interesting and worth further research, like "what is the sentiment towards different disasters and why" and "how does the country of the speaker affect which disasters he is talking about". -->

## You can find the description of main results on our website: [adahivemind.github.io](https://adahivemind.github.io/).

<!-- Given that a comprehensive analysis of these research questions might be challenging, we discard other related and interesting questions like "what is the sentiment towards different disasters and why" and "how does the country of the speaker affect which disasters he is talking about". -->

<!-- ADDITIONAL DATASETS -->
<h2 id="additional-datasets"> :floppy_disk: Additional datasets</h2>

Besides loading and doing exploratory data analysis on [Quotebank](https://github.com/epfl-dlab/Quotebank) in [`quotes_eda.ipynb`](quotes_eda.ipynb), we used two additional datasets:
- [The international disasters database](https://public.emdat.be/data), loaded and analysed in [`disasters_eda.ipynb`](disasters_eda.ipynb)
- [World Data Bank](https://databank.worldbank.org/source/world-development-indicators), loaded and analysed in [`wdi_eda.ipynb`](wdi_eda.ipynb)

<!-- Besides these datasets, we use [GDELT Geographic Lookup of Domains](https://blog.gdeltproject.org/mapping-the-media-a-geographic-lookup-of-gdelts-sources/) and might use public disaster tweets datasets like the one in [this kaggle challenge](https://www.kaggle.com/c/nlp-getting-started/overview) to use them for disaster quotes classification, if the models prove to be of desired success. -->

<!-- ADDITIONAL DATASETS DISASTERS -->
<h3 id="additional-datasets-disasters"> 1. Disasters</h2>

Data source: [The international disasters database](https://public.emdat.be/data)

We use [the international disasters database](https://public.emdat.be/data) to introduce natural disasters of this century with their most important attributes.
<!-- , as we want to find the connection between the attributes of a disaster and the length (or distribution) of the time these disasters are talked about in quotes. -->
<!-- To enumerate the most important attributes introduced with this dataset, we get the disaster type, total deaths, total damage in dollars, country of disaster, the date, and the reconstruction cost. -->
<!-- There are also some disaster-type specific attributes like the magnitude of an earthquake on a Richter scale. -->

This dataset was compiled from various sources including UN, governmental and non-governmental agencies, insurance companies, research institutes, and press agencies. <!-- As there can be conflicting information and figures, CRED has established a method of ranking these sources according to their ability to provide trustworthy and complete data. --> In the majority of cases, a disaster will only be entered into EM-DAT if at least two sources report the disaster's occurrence in terms of deaths and/or affected persons.

In the [`disasters_eda.ipynb`](disasters_eda.ipynb) notebook, we have loaded, pre-processed and cleaned, analyzed, and visualized the dataset. 

<img src="./images/num_disasters_per_country.png" title="Number of disasters per country (2008-2020)" />

<!-- WORDL DEVELOPMENT INDICATORS -->
<h3 id="additional-datasets-wdi"> 2. World Development Indicators</h2>

Data source: https://databank.worldbank.org/source/world-development-indicators

<!-- To supplement the disaster dataset, we have selected 55 different world development indicators from the [World Data Bank](https://databank.worldbank.org/source/world-development-indicators). We took the per-year data from the year 2000 to the year 2020 and for all available countries. Detailed indicator description is given in the metadata csv file `databank_wdi_metadata.csv`, including the source, unit of measure, periodicity, aggregation method, statistical concept and methodology, development relevance, and limitations. Raw data is saved in `databank_wdi_data.csv`, with the preprocessed dataset created in this notebook saved in `databank_wdi_data_clean.csv`. -->

One important factor in how much people talk about a disaster might be the country and its attributes. In this dataset, the most important development indicators of the country can be found, for example GDP, population, and fertility rate. Detailed per-indicator source and description is given in `databank_wdi_metadata.csv`. We would like to observe whether there is a connection between these indicators and the length and distribution of time they talk about the disaster.

In the [`wdi_eda.ipynb`](wdi_eda.ipynb) notebook, we have loaded, pre-processed and cleaned, analyzed, and visualized the dataset.


<!-- WORLD DEVELOPMENT GDELT -->
<h3 id="additional-datasets-gdelt"> 3. GDELT Geographic Lookup of Domains</h2>

Data source: https://blog.gdeltproject.org/mapping-the-media-a-geographic-lookup-of-gdelts-sources/

The geographical location of newspapers could affect the citations contained in them. Although the quotes in the Quotebank dataset contain links to the article in which they were found, we cannot find out the true geographical location of the news source from the link itself. E.g. theguardian.com and nytimes.com both use .com top-level domain, but they are reporting events in different countries. That's why we decided to choose a GDELT dataset that associates a particular domain with the right country from which that news source comes. This dataset was created from the enormous GDELT dataset and used the fact that news outlets cover events physically proximate to them far more often than they do events on the other side of the world.

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
    │   │   ├── emdat_public_2021_11_06_clean.csv
    │   │   └── emdat_public_2021_11_06.csv
    │   │
    │   └── wdi
    │       ├── databank_wdi_data.csv
    │       └── databank_wdi_metadata.csv
    │
    ├── quotes_eda.ipynb
    ├── wdi_eda.ipynb  
    ├── earthquake_quotebank_extraction.ipynb 
    ├── media_influencing_factors.ipynb.ipynb  
    └── disasters_eda.ipynb
    
    
Detailed description: 
- [`quotes_eda.ipynb`](quotes_eda.ipynb): this includes exploratory data analysis on the quotebank
- [`wdi_eda.ipynb`](wdi_eda.ipynb): this notebook is used to examine the Word Development Indicators dataset
- [`disasters_eda.ipynb`](disasters_eda.ipynb): this is also for examination of the additional dataset, this time the Disaster dataset is in the focus
- [`media_influencing_factors.ipynb`](media_influencing_factors.ipynb): this notebook is for putting all things together, merging our dataset and analysing the connections
- [`earthquake_quotebank_extraction.ipynb`](earthquake_quotebank_extraction.ipynb): this notebook consists of the filtering of earthquake related quotes.
 
<!-- METHODS -->
<h2 id="methods"> :mag: Methods</h2>

<!-- <h3> Dask </h3> -->

To handle the large Quotebank dataset, we have set up a pipeline using Dask, a flexible parallel computing library for analytics. Dask scheduler dashboard during the run of a long task is shown in the image bellow.

<img src="images/dask_scheduler_dashboard.jpeg" title="Dask scheduler dashboard" />

<!-- <h3> Answering the research questions </h3> -->

In tackling the research questions, the crucial component was to classify whether a specific quote is talking about a disasters or a specific event. The method we proposed to find whether a quote is about a certain disaster is to do simple text searching to match the expected words. These words might include some details about the place where the disaster happened. <!--Depending on the scalability of the method, we would perform the analysis on a subset of the disasters. Assuming that a number of disasters happen in places that usually do not receive much media attention (like Fukushima in world news), we could for example select these disasters and then search for quotes that mention these places, hoping for a good precision.-->

<!--To evaluate the precision of the proposed methods, we hand-labeled whether a sample of, for example, 100 quotes that were detected by the method are true positives or false positives.-->

In overall, we experienced that the model works the best with the event name and the event type, so we decided to filter the quotes with this methodology. In the following mini case study, we can see the same behaviour. This is about the Haiti earthquake in 2010, which demanded the highest number of death during the course of time. The two figures below show the frequency over time of quotes that contain haiti+earthquake (top figure) and haiti+earthquake+2010 (bottom figure). The details are in the [`quotes_eda.ipynb`](quotes_eda.ipynb) notebook.

<img src="images/haiti_case_study.jpeg" title="Quotes containing haiti+earthquake, quotes containing haiti+earthquake+2010 " />

We would also wanted to investigate how the models trained on disaster tweets datasets used for classifying natural disaster in the tweets will perform on the quotes from the Quotebank. To do so, we proposed to train simple BERT based sentence encoding with a Logistic Regression Classifier.

<!-- PROPOSED TIMELINE -->
<!--<h2 id="timeline"> :calendar: Proposed timeline</h2>


Nov 26 (HW2 Deadline): Quote - disaster matching with simple text search and manual labeling of quotes

Dec 3: Disaster classification using pre-trained NLP models (an attempt at NLP transfer learning) and exploration of media influencing factors (total deaths, total damage in dollars, country of disaster etc.)

Dec 10:  Evaluation and visualization of the outcomes, implementation of potential improvements and notebook finalization

Dec 15: Preparation of the data storyline and the website

Dec 17: Proofreading, minor adjustments and submission (Everyone)-->


<!-- PROPOSED TIMELINE -->
<h2 id="organization"> :dart: Organization within the team</h2>

Batuhan - 
NLP model training, preparation and deployment of the website

Frano -
NLP model training, labeling of the quotes, outlining and enriching the data storyline

Hilda -
Exploration of media influencing factors, valuation and visualization of the outcomes, labeling the quotes. 

Lovro -
Labeling of the quotes, quote-disaster matching, valuation and visualization of the outcomes.

<!-- QUESTIONS FOR TAs -->
<!-- <h2 id="questions-for-tas"> :question: Questions for TAs (optional)</h2>

Add here any questions you have for us related to the proposed project. -->
