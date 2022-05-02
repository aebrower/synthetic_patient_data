## Creation of Synthetic Patient Data 

You can use the [editor on GitHub](https://github.com/aebrower/synthetic_patient_data/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/aebrower/synthetic_patient_data/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

**Synthetic Data:** computationally derived from generative models to, **theoretically**, preserve statistical properties of the original data while protecting from privacy attacks

## Does it actually preserve statistical properties of the original data?
**Yes.** In most cases.
Studies have found that computationally derived (synthetic) data has no statistically significant difference from its original dataset.
The patterns presented and results derived from the two datasets are comparative.
However, if the original dataset does not contain a lot of data on a small, rural population, the information from the synthetic dataset is not relevant or useful.

## What are the major drawbacks of synthetic datasets?
- **Privacy-Utility Tradeoff:** information-rich datasets which are extremely valuable for statistical analyses always contain enough information to conduct privacy attacks
- If the synthetic dataset retains characteristics from the original dataset with high accuracy (this is what makes it so useful and relevant), it simultaneously enables adversaries to extract sensitive information about individuals.
- Hard to predict and decrease this risk
- Rare diseases that do not have much information are still hard to create in synthetic settings.

# What is Synthea?
It is a program created by MITRE to generate fully synthetic outputs about patients by accepting only publicly available information and health statistics as inputs.

**Goals of Synthea**
1. Data generation is based on models of clinical workflow and disease progression, so it can be easily modified and refined.
2. The temporal aspect of the model covers a synthetic patient’s entire lifetime instead of just a specific disease or condition.
3. Collaboration with experts from clinical and technical backgrounds supports the validity of the model.

## How does Synthea address the problems regarding synthetic datasets?
- Since the information Synthea uses to create its data is all publicly available, there is no privacy risk present.
- Due to its easily refinable nature, demographics of the population created by Synthea that do not match real demographics can be modified and refined easily by the creators with help from experts.
- Synthea models a patients’ entire lifetime rather than a singular encounter, so it can be parameterized in the future to take into account realistic interactions that define health systems (e.g. practices that deviate from standard guidelines and introduce variations in healthcare quality).

# How to use Synthea?
- Synthea is designed for non-clinical uses where access to real data is not mandatory. It's best used for creating innovative idea, education or testing where clinical data is needed
- Synthetic data sets are created from the command line where you can specify details about the data that you want to create

## Synthea requirements
To use Synthea, you will need:
- Java installed: https://www.java.com/en/
- To clone Synthea: 
```
  git clone https://github.com/synthetichealth/synthea.git
```

## Example case
To create synthetic health records for a population of size 10. Run the following command:
```
run_synthea -p 10
```
When this command runs each of the patients will run through the 72 modules and 76 submodules that are contained within Synthea. These module determine the health outcomes for the patients. Your output should look like the following:

```
Running with options:
Population: 10
Seed: 1651508269731
Provider Seed:1651508269731
Reference Time: 1651508269731
Location: Massachusetts
Min Age: 0
Max Age: 140
3 -- Alan320 Torphy630 (16 y/o M) Walpole, Massachusetts DECEASED
7 -- Antoine384 Emmerich580 (22 y/o M) Lexington, Massachusetts
6 -- Hong136 Kihn564 (45 y/o F) Boston, Massachusetts
1 -- Lloyd546 Cummings51 (60 y/o M) Saugus, Massachusetts
5 -- Kathlyn335 Pouros728 (59 y/o F) Attleboro, Massachusetts
2 -- Abraham100 Leannon79 (65 y/o M) Sudbury, Massachusetts
4 -- Christian753 Altenwerth646 (66 y/o M) Chelsea, Massachusetts
8 -- Darrell400 Shields502 (86 y/o M) Somerville, Massachusetts DECEASED
10 -- Kenneth671 Morar593 (0 y/o M) Boston, Massachusetts
9 -- Rocco842 Mohr916 (31 y/o M) Turners Falls, Massachusetts
3 -- Chance908 Runolfsson901 (58 y/o M) Walpole, Massachusetts
8 -- Genaro214 Volkman526 (66 y/o M) Somerville, Massachusetts DECEASED
8 -- Sidney996 Herman763 (93 y/o M) Somerville, Massachusetts
Records: total=13, alive=10, dead=3
```

Your specific outcome will vary between runs. However, by default 10 years of history for each patient from Massachusetts is created and written to the output files. All the data related to the patients are placed in their own JSON fille in the output/fhir folder. Also included by default is the output relating to the providers and hospitals that will potentially tend to patients. 



