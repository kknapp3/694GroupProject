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
  &nbsp;&nbsp;&nbsp;  $10.86 Billion &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 11.22 Million &nbsp;&nbsp;
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



{% capture includeGuts %}
{% include fig1_1.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

Aenean placerat dolor eget sem dapibus facilisis. Nullam sem purus, semper non orci eget, gravida auctor tortor. Nulla nec sagittis ex. Donec luctus pulvinar orci id porta. Maecenas sagittis lacus eu efficitur placerat. Pellentesque laoreet elementum leo eu viverra. Aliquam efficitur orci in risus fermentum, eu blandit risus auctor. Aenean elementum sed augue et scelerisque. Maecenas aliquet, metus vitae maximus pellentesque, risus enim tincidunt sem, a semper tellus urna ac justo. Morbi mauris risus, tempor vitae aliquet sit amet, euismod nec lectus. Aliquam vitae nisl rutrum, pellentesque lectus vitae, iaculis purus.

{% capture includeGuts %}
{% include fig1_2.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 2 How many recipient records each state?

Aenean placerat dolor eget sem dapibus facilisis. Nullam sem purus, semper non orci eget, gravida auctor tortor. Nulla nec sagittis ex. Donec luctus pulvinar orci id porta. Maecenas sagittis lacus eu efficitur placerat. Pellentesque laoreet elementum leo eu viverra. Aliquam efficitur orci in risus fermentum, eu blandit risus auctor. Aenean elementum sed augue et scelerisque. Maecenas aliquet, metus vitae maximus pellentesque, risus enim tincidunt sem, a semper tellus urna ac justo. Morbi mauris risus, tempor vitae aliquet sit amet, euismod nec lectus. Aliquam vitae nisl rutrum, pellentesque lectus vitae, iaculis purus.

{% capture includeGuts %}
{% include fig2.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 3 How much money in total for each state by manufactures?

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

{% capture includeGuts %}
{% include fig3.html %} 
{% endcapture %}
{{ includeGuts | replace: '    ', ''}}

#### 4 Payment Received per State

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent feugiat ex quis sem feugiat luctus. Morbi ac congue nibh. Etiam mi sapien, faucibus sit amet nulla sit amet, ullamcorper facilisis neque. Fusce quis ultrices erat. Etiam sem dolor, vulputate ac magna id, aliquam tincidunt justo. Duis porttitor nec ipsum ullamcorper iaculis. Aliquam id justo pretium, sollicitudin lectus ac, viverra libero. Donec ac pellentesque elit, non volutpat orci. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Aenean justo eros, tincidunt quis augue ac, maximus dapibus sapien. Donec in felis diam. Nulla dapibus urna in molestie porta. Donec malesuada eu urna eget eleifend. Ut tincidunt molestie est non blandit.

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

>  Nore: In the first column, E means the number of executors and W means the number of workers.