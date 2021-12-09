## Open Payment Data Visualization

### What is OpenPayment?

<img src="./images/openpay.jpg" width="300" align="right" style="padding-top:10px">Open Payments is a national disclosure program that promotes a more transparent and accountable health care system. Open Payments houses a publicly accessible database of payments that reporting entities, including drug and medical device companies, make to covered recipients like physicians.

The data we tried to analuze and visualize here is the data gathered in the program year 2019 (January 1, 2019–December 31, 2019) and published in the year 2021. 

### Terminologies

**1. Nature of Payments**

The nature of payments is in the form of a severance payment considered to be reasonable by the Bank. It helps to understand the different types of payments that must be reported to Open Payments. The common types of payments include,

- Food and beverage
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




The Open Payments data has a size **5.7 GB** and we also combined it with a drug dataset of **3.1 GB**. Because of the size of the data, we used Spark Clusters for processing the data on AWS, and then made the plots by Plotly. The efficiency of using different EMR machines will be stated in our performanc summary at the end of this report.

### Data Visualization

#### 1 Payment Distribution

These are figures about the distribution of payment in the Program year 2019. We made these figures to understand what is the most common payment amount. The data is very unbalanced as a right-skewed distribution. We split the distribution on the payment of 50 so that we can have better understand how the data appears. We actually took a sample of 48,577 records from the whole set to keep the size of the plot (113 MB) from growing excessively large. As it is displayed in the first part of distribution, we can observe that most of the payment amounts are between ​\$10 to ​\$25.

{% capture includeGuts %}
{% include fig1_1.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

Then in the second part of distribution, we observe a quick decay of the counts. The data we have selected in this plot are the payments from \$50 to \$2,000.  Although there are also some payments larger than \$2,000 but they rarely happen with a porportion of around 2.8% across the whole set. So we finally decided not to include them in the visualization.

{% capture includeGuts %}
{% include fig1_2.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 2 How many recipient records each state?

Next, we examined which states are most active in the Open Payment Program. This figure basically shows how many recipient records were gathered in each state in the Program year 2019. The result shows that California, Texas, Florida, and New York were most active in terms of number of records. This is likely due to these states having higher populations. We will analyze this further in figure 4.

{% capture includeGuts %}
{% include fig2.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 3 How much money in total for each state by manufactures?

Now that we know which states receive more money than others, what about the manufactures? In the present figure, we observe that the applicable manufacturers, group purchasing organizations, or drug and medical device companies in California, Illinois, Indiana, Massachusetts, and New Jersey have higher payment totals than the other states.

{% capture includeGuts %}
{% include fig3.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 4 Recipient Payment Records per Capita per State

Let's continue with figure 2. In figure 2, we observe that some states have more records than others. But does that mean these states were more active in this program? Probably not, we have guessed that it is probably because of the population. The present plot is the amount of money regularized by the population in each state and now we can find out that most of the states are relatively on the same page. Massachusetts is actually an outlier in this visualization and we speculate this is because it has more medical institutions than the other states.

{% capture includeGuts %}
{% include fig4.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 5 Payment Received by Physician Specialty

To continue with our discussion, we also have a look at the top five types of physicians that get the most of the payments. It turns out that orthopaedic surgery, neurology, and internal medicine physicians received the most payments in the Program Year 2019.

{% capture includeGuts %}
{% include fig5.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 6 Natural of Payments by Records

We previously discussed the nature of payments, and we explore what types of payments were most commonly made in 2019. From this figure below, we observe that the most common type of payment is food and beverage at about 87%. Some other top ranked payment-types were travel and lodging, compensation, education, etc.

{% capture includeGuts %}
{% include fig6.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 7 Natural of Payment by Amount of Money

Instead of just viewing the number of the records for each type of payment, we would also like to know which types contribute the largest amount of money. The present figure shows that Royalty or License payments account for most of the payments (about 1.58 billion), even though they do not rank high by virtue of number of records.

{% capture includeGuts %}
{% include fig7.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 8 Drug Cost and Payment Received Relationship

So the final question we pose: what is the impact of the these payments? To answer this, we combined the Open Payment dataset in 2019 together with the drug cost dataset in 2019 to produce the following scatter plot. The results show that we see higher drug costs in states with higher total amounts of payments received. 

{% capture includeGuts %}
{% include fig8.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

### EMR Performance

The present plots and analysis were created using AWS EMR, Apache Spark, and Plotly. We tested several Spark operations out on different EMR clusters to gauge the differences in their performance. The results show that we can add more workers to yield better performance. In addition, the Intel chip (m5.xlarge based on Intel Xeon Platinum 8000) outperforms AMD's equivalent chip (m5a.xlarge based on AMD EPYC 7000). Furthermore, chips with higher clock rates (m5zn.xlarge based on Intel Xeon Scalable processors with a frequency up to 4.5 GHz) perform better even when with sightly less RAM (random access memory) of 15GB and fewer worker nodes than the ordinary Intel chips.

<img src="./images/Performance.png" align="center" style="padding-top:10px">

 *Note*: In the first column, **E** represents the number of executor nodes and **W** represents the number of worker nodes in the EMR cluster.
