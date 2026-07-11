
# eu_public_consultations

Public consultation is a process in which the public's input on matters affecting them is sought. Its main objectives are in improving the efficiency, transparency and public involvement in large-scale projects or laws and policies. Research on public consultation is well-established field of political science, however, utilisation of computational analysis have been limited to analysing quantitative data from closed-choice questionares. Currently existing corpora containing public consultation responses currently focus on a single topic. Development of multi-thematic, metadata-rich public consultation corpus would enable and facilitate utilisation of NLP techniques in research on public consultation.

## Data source

"Have Your Say" is a public consultation platform available on the European Comission's website: https://ec.europa.eu/info/law/better-regulation/have-your-say_en. It gathers opinions and views on policies and laws which are currently in developement by the European Comission. Details about each initiative are published with appropriate documents, such as proposals, draft acts, reports, etc. During feedback period public and private entities, both from and outside of EU, can write their opinion on the initiative.

Due to lack of a documented API and ability to download the data in a bulk, the resource was not easly usable for computational analysis (at the time of creation of this repository in September 2023).
The following dataset was scrapped through undocumented API of the platform. It contains texts of all feedbacks available on 11.09.2023 with its metadata. Feedbacks which violated the Comission's feedback rules were removed from the site by the EC.

## Files

This repository consists of the following files:

- initiatives.csv, summaries.csv, feedbacks.csv - Datasets originating from 'Have Your Say' platform (see data structures below)
- pubcons_analysis_ready.ipynb - Jupyter notebook with notebook z opisem projektu, danych, analizami
  pubcons_scrapper.ipynb - Jupyter notebook with the scrapper z kodem do zebrania danych z konsultacji publicznych poprzez API
  vis.html - wizualizacja utworzona w notebooku z analizą danych

## Datasets' details

### Structure of initiatives.csv

| Column            | Description                       |
| ----------------- | --------------------------------- |
| id                | Initiative's id                   |
| shortTitle        | Title of the initiative           |
| foreseenActType   | Type of act                       |
| topics            | Json containing topic description |
| feedbackStartDate | Start date of feedback period     |
| feedbackEndDate   | End date of feedback period       |


### Structure of summaries.csv

| Column    | Description                       |
| --------- | --------------------------------- |
| summary   | Summary of the initiative         |
| groupId   | Initiative id                     |
| id        | Publication id                    |
| reference | Json containing topic description |


### Structure of feedbacks.csv

| Column              | Description                                              |
| ------------------- | -------------------------------------------------------- |
| language            | Coded language of feedback                               |
| id                  | Feedback id                                              |
| country             | Coded country of author                                  |
| organization        | Name of author's afiliation                              |
| status              | Feedback status: Published, rejected, anonymised_by_user |
| surname             | Author's surname                                         |
| firstname           | Author's firstname                                       |
| feedback            | Feedback text                                            |
| userType            | Type of user                                             |
| companySize         | Company size                                             |
| referenceInitiative | Initiative reference number                              |
| publicationId       | Publication id                                           |
| publicationStatus   | Status of feedback publication                           |
| dateFeedback        | Date of feedback publication                             |
| attachments         | Attached files information                               |
