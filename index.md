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

