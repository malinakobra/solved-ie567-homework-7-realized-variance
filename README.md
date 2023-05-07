Download Link: https://assignmentchef.com/product/solved-ie567-homework-7-realized-variance
<br>
<strong>Gather the data.</strong> (0 points, but necessary for the other questions) Login in to WRDS, go to the data vendor TAQ, and find the millisecond “Consolidated Trade” data:

Click on “Consolidated Trades” and you will see:




You want the data from January 2017, the time range 9:30:00 – 16:00:00 (the regular trading day), root symbol JPM, and the fields “Exchange that issued the trade,” “Trade Sale Condition,” “Volume of trade,” “Price of trade,” and “Trade Correction Indicator.” I recommend against downloading data outside the time range 9:30:00 – 16:00:00 or fields that you do not need. It might be convenient to download and process the data for one day at a time rather than try to download and process the data for the entire month at once.




If you download the data in .csv format, the columns will be headed DATE, TIME_M, EX (= exchange), SYM_ROOT, SYM_SUFFIX, TR_SCOND (= trade sale condition), SIZE, PRICE, and TR_CORR (= trade correction indicator).  You should use the data for which SYM_SUFFIX is blank (these are trades in JPM common stock), TR_SCOND = @ (these are regular trades), and TR_CORR = 0.




For each date in January 2017, construct a sequence of trade prices at one-minute frequency, starting from 9:31 am and ending at 4:00 pm.  To this, for each minute, set the price equal to the trade price of the last trade that occurred on or prior to the minute.  For example, for the minute 9:37, set the price to be equal to the trade price of the last regular trade with trade time less than or equal to 9:37:00.000.

<ol>

 <li><strong>Realized variance when the market is open for a liquid stock.</strong> (3 points) For each of the 20 trade dates during January 2017, compute the 1-minute continuously compounded returns from 9:45 am to 4:00 pm (the first return interval should be from 9:45 am to 9:46 am, and the last should be from 3:59 pm to 4:00 pm.).  Use these continuously compounded returns to compute the realized variance during the period when the market is open. (This is what Christoffersen calls RV<em><sub>t</sub></em><sup>OPEN</sup>.)  What is the average of the 20 estimates?</li>

</ol>

<ol start="2">

 <li><strong>Average realized variance estimator </strong>(3 points) Compute 2-minute, 5-minute, 10-minute, and 15-minute continuously compounded returns. Use these returns and the average realized variance estimator to estimate the realized variance on each of the 20 days based on returns at 2minute, 5-minute, 10-minute, and 15-minute frequency. For each return interval, what is the average (across days) of the realized variance estimators?  (Your answer should consist of four numbers, one each for the 2, 5, 10, and 15-minute intervals.)</li>

</ol>




When the return interval is greater than one minute and the market is not open 24 hours, the average realized variance estimator when the market is open, RV<em><sub>t</sub></em><sup>OPEN</sup>, might seem not quite right.  For example, there are 25 15-minute returns based on the prices at 9:45, 10:00, 10:15,  …, 15:45, 16:00, but only 24 based on the prices at 9:46, 10:01, 10:16,  …, and 15:46.  There are also only 24 returns in the other series of 15-minute returns.  (The 2, 5, and 10-minute returns share the same problem.) Should you somehow adjust for this?  If so, how?




<em>Remark:</em>  This is not in the textbook or lecture notes.  You have to think about it, and figure out what to do.




Do your estimates of realized variance increase or decrease as the return interval becomes longer?  What is the ratio of the average (across days) average realized variance based on 15minute returns to the average (across days) realized variance based on 1-minute returns?  What is the ratio of the average (across days) average realized variance based on 15-minute returns to the average (across days) average realized variance based on 10-minute returns?




<ol start="3">

 <li><strong>Autocorrelation of realized variance. </strong>(1 point)  Use the 20 15-minute average realized variance estimates that you computed to answer Question 2 to compute the autocorrelation of realized variance. What is the autocorrelation of this time series of realized variance estimates?</li>

</ol>




<ol start="4">

 <li><strong>24-hour realized variance estimator. </strong>(2 points) Use the 15-minute average realized variance estimates from Question 2 for each of the 20 days and the two different approaches on slides 8 and 9 of the lecture notes IntradayVolModelling-04.pptx to compute estimates of the 24hour variance of JPM for each of the 20 days.  (Because there are two approaches and 20 days, you should compute a total of 2 ×20 = 40 estimates of the realized variance.)  What are the averages (across days) of the variance estimates computed using the two approaches?</li>

</ol>




<em>Remark.</em>  Your answer to this question should consist of two numbers.  You will have to collect the JPM opening and closing prices.  Yahoo Finance is a convenient source.







<ol start="5">

 <li>(1 point) The Chinese stock exchanges are open four hours per day, from 9:30 – 11:30 a.m. and then from 1:00-3:00 p.m. Suppose you use data from the period when the Shanghai Stock Exchange is open to compute the realized variance of the common stock of China Construction Bank during the period when the Shanghai Stock Exchange is open.  Call the estimate RV<sup>Open</sup>.  Please briefly describe two ways to adjust RV<sup>Open</sup> to obtain an estimate of the variance over a 24hour period?</li>

</ol>