## Open Payment Data Visualization

### What is OpenPayment?

<img src="./images/openpay.jpg" width="300" align="right" style="padding-top:10px">Open Payments is a national disclosure program that promotes a more transparent and accountable health care system. Open Payments houses a publicly accessible database of payments that reporting entities, including drug and medical device companies, make to covered recipients like physicians.

The data we tried to analuze and visualize here is the data gathered in the program year 2019 (January 1, 2019–December 31, 2019) and published in the year 2021. 

### Terminologies

**1. Natural of Payments**

The natural of payments is in the natrual of a severance payment considered to be reasonable by the Bank. It helps to understand the different types of payments that must be reported in the open payment. The common types of payments include,

-  Food and beverage
- Consulting fee
- Education
- Research
- Travel and lodging
- Etc.

**2. Program Participants**

There are two groups of participants in the Open Payments program. **Reporting entities** include applicable manufacturers and group purchasing organizations, or drug and medical device companies. **Covered recipients** include:

- Any physicians (with the exception of medical residents) who are not employees of the reporting entity
- Certain non-physicians
- Teaching hospitals that receive payments for Medicare direct graduate medical education (GME), inpatient prospective payment system (IPPS) indirect medical education (IME), or psychiatric hospital IME programs

### Exploratory Data Analysis (EDA)

In the program year 2019, the total US dollars involved and the total number of published records are,

<center>
<span style="font-size:20px;color:#47965d;"> 
   &nbsp;&nbsp;&nbsp;&nbsp; Total US Dollar Value &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Total Records Published 
</span>
<br>
<span style="font-size:20px;font-weight:bold;"> 
  &nbsp;&nbsp;&nbsp;  $10.53 Billion &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.67 Million &nbsp;&nbsp;
</span>
</center>



The numbers of physicians and manufactures involved in the Program year 2019 are,

<center>
<span style="font-size:20px;color:#47965d;"> 
   &nbsp;&nbsp;&nbsp;&nbsp; Total Number of Physicians &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Total Number of Manufactures
</span>
<br>
<span style="font-size:20px;font-weight:bold;"> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  623 Thousand&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1657&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span>
</center>




The Open Payments data has a size **5.7 GB** and we also combine it with a drug dataset of **3.1 GB**. Because of the size of the data, we use Spark Clusters for processing the data on AWS, and then made the plots by Plotly. The efficiency of using different EMR machines will be stated in the last part.

### Data Visualization

#### 1 Payment Distribution

These are figures about the distribution of payment in the Program year 2019. We made these figures to understand what is the most common amount payment. The data is very unblance as a right-skewed distribution. We split the distribution on the payment of 50 so that we can have better understanding of how the data looks like. We actually took a sample of 48,577 records from the whole set or the plot will be over large (over 113 MB). As it is displayed in the first part of distribution, we can observe that most of the payment amounts are between ​\$10 to ​\$25.

{% capture includeGuts %}
{% include fig1_1.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

Then in the second part of distribution, all we can observe is a quick decay of the counts. The data we have selected in this plot are the payments from \$50 to \$2,000.  Although there are also some payments larger than \$2,000 but they rarely happen with a porportion of around 2.8% across the whole set. So we finally decided not to include them in the visualization.

{% capture includeGuts %}
{% include fig1_2.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 2 How many recipient records each state?

Next, let's take a look at which states are active in the Open Payment Program. This figure basically shows how many recipient records gathered in each state in the Program year 2019. The result shows that California, Texas, Florida, and New York are pretty active in these records. This probably because these states has a higher population. We will analyze that more in the figure 4.

{% capture includeGuts %}
{% include fig2.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 3 How much money in total for each state by manufactures?

Now that we know some states receive more moneys than the others, so what about the manufactures? In the present figure, it shows that the applicable manufacturers, group purchasing organizations, or drug and medical device companies in California, Illinois, Indiana, Massachusetts, and New Jersey.

{% capture includeGuts %}
{% include fig3.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 4 Recipient Payment Records per Capita per State

Let's continue with the figure 2. In the figure 2, we can observe that some states has more records than the others. But does that mean these states are more active in this program? Probably not, we have guessed that it is probably because of the population. The present plot is the amount of money regularized by the population in each state and now we can find out that most of the states are on the same page. Massachusetts is actually an outlier in this visualization and we guess this is because it has more medical institutions than the other states.

{% capture includeGuts %}
{% include fig4.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 5 Payment Received by Physician type

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

{% capture includeGuts %}
{% include fig5.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 6 Payment Received by Specialty

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

{% capture includeGuts %}
{% include fig6.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 7 drug cost against payment received per state

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

{% capture includeGuts %}
{% include fig7.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 8 nature of payment percentage

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

{% capture includeGuts %}
{% include fig8.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

### EMR Performance

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

<img src="./images/Performance.png" align="center" style="padding-top:10px">

 *Note*: In the first column, **E** means the number of executors and **W** means the number of workers.