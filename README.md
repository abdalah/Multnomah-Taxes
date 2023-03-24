# Multnomah-Taxes

Looking at the amount people pay in taxes per dollar amount of income. Note that all the brackets below are for "Single"" filers only. Feel free to use the data and code provided to recreate everything for any of the other filing types.


## Brief Description on Taxes Involved

### Federal Taxes

Using the following sources, I was able to find the right amount of federal tax brackets for both capital gains and regular income.


#### Federal Capital Gains Taxes
These show up as the following:

https://www.nerdwallet.com/article/taxes/capital-gains-tax-rates

|Bracket Start |Bracket End |Rate |
|:-------------|:-----------|:----|
|\$0           |\$41,675    |0%   |
|\$41,676      |\$459,750   |15%  |
|\$459,751     |-           |20%  |


#### Federal Income Taxes

Note that these are the income taxes for 2023 as income taxes change year over year.

https://taxfoundation.org/2023-tax-brackets/

|Bracket Start |Bracket End |Rate |
|:-------------|:-----------|:----|
|\$0           |\$11,000    |10%  |
|\$11,000      |\$44,725    |12%  |
|\$44,725      |\$95,375    |22%  |
|\$95,375      |\$182,100   |24%  |
|\$182,100     |\$231,250   |32%  |
|\$231,250     |\$578,125   |35%  |
|\$578,125     |-           |37%  |

### State Taxes

Since Oregon taxes capital gains as income, the tax brackets are the same for income and capital gains. Note that these are the tax brackets for 2023 as 

https://www.incometaxpro.net/tax-rates/oregon.htm

|Bracket Start |Bracket End |Rate  |
|:-------------|:-----------|:-----|
|\$0           |\$3,750     |4.75% |
|\$3,751       |\$9,450     |6.75% |
|\$9,451       |\$125,000   |8.75% |
|\$125,001     |-           |9.9%  |


### Taxes per Income

The difficulty here is comparing know how much people pay in taxes with all the different tax brackets. On top of that, tax payers pay the bracket rate for each tax bracket they are a part of. For example, if were in the highest tax bracket and made \$125,100 in Oregon, then your Oregon taxes would be the following:

$3750 * .0475 + (9450-3750) * .0675 + (125000-9450) * .0875 + (125100-125000) * .099 = 10683.4$ Or $8.5\\%$

To graph your taxes (both federal and state) per income, you would get the following:

![](https://github.com/abdalah/Multnomah-Taxes/blob/main/Output/Multnomah%20County%20Taxes.png?raw=true)

Note here that you see a green line as well. This is created by adding the ERA tax for Multnomah County which is a .75% on capital gains.

#### The Graphic

The graphic above is created using R with the `tidyverse` and `here` packages. The percent of income is calculated at each dollar amount that appears on the x-axis. The script is in the `Tax Percent by Tax Brackets.Rmd` file.
