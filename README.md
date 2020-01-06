# Project-Instkart_Market_Explotary-Analysis-and-LGB-ML-Modleing
A Explotary Data Analysis of Instakart Market data of 3 Million data oreder of 200,000 users to identify the item user will buy again. 

<!-- wp:heading {"level":3} -->
<h3><strong>Business Problem:</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Our stakeholder, Instacart is searching for the marketing business solution. With&nbsp;&nbsp;200,000&nbsp;active customers, they have issue with future prediction of customer and regular use of app for purchasing. Their main aspect it to identify following problems:</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true,"type":"1"} -->
<ol type="1"><li>Which Product will an Instacart consumer purchase again?</li><li>How individual departmental contribution and performance important for weekly and hourly performance?</li><li>Identify required resource insights for future human resource requirement of departmental level.</li></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3><strong>Data Understanding:</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Data are collected from various department and previous order history.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Here company provide their data in csv file form and the total datasets are as follow:</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
<h5>  [1] aisles.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Contain data of aisles id and its name&nbsp;</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":5} -->
<h5>  [2] departments.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Contain department id and their name&nbsp;</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":5} -->
<h5>  [3] order.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Contain important data of order_id, user_id, order_number, order_dow, order_hour_of_day, day_since_prior_order made</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":5} -->
<h5>  [4] order_products__train.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Information about order_id, product_id, add_to_cart_order, reordered items</li><li>It’s the main information of our training set and order after first order</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":5} -->
<h5> [5] orders_products__prior.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Information about order_id, product_id, add_to_cart_order, reordered items</li><li>It’s about the order done before and reordered again, if there is NAN, means no reorder happen In product history</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":5} -->
<h5> [6] products.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Product_id, product_name, aisle_id, department_id</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":5} -->
<h5>  [7] sample_submission.csv</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Its prior submission derived by the Company for their resultant requirement.</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Pre-Analysis of data info and data description shows fully detailed data without any loss or missing data. Our data are also in same form of data type across all spreadsheets. So all spreadsheets are identical and best in quality for analysis.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>Data preparation and </strong>Exploratory <strong>analysis:</strong></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3><strong>Construct, Integrate and Dataset Formation:</strong></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Train, Test and prior values in total dataset.</li><li>Max no. of user’s orders and its occurrence frequency for identify user’s buying pattern and company’s current market status.(bar-chart)</li><li>Identify no. of order rate with weekday pattern for buying patterns, customer demand, product availability and server load. (bar-chart)</li><li>Order frequency for week’s hourly data pattern for identify rushing hours.(bar-chart)</li><li>Merge two results and understand&nbsp; best hour in week for product selling.(heatmap)</li><li>Revels&nbsp; client’s reordered frequency (based on prior ordered data).</li><li>Reordering percentage of prior and train dataset.</li><li>Identify products without reordering. (order once and only once) Note: its different from&nbsp; process of reordering percentage difference.</li><li>Counting&nbsp; Orders for number of&nbsp; purchasing products.</li><li>Merge products, aisle_id, and department_id datasets into product_order_prior.</li><li>Format a list of tables for Ordered products and their order counting to get insight in customer preference understanding. (bar-graph)</li><li>Find out most useful aisle based on total orders form aisle data. (bar-graph)</li><li>Find out importance of department, based on their contribution in ordering and reordering data. (line-graph, pie-chart)</li><li>Value of Departmental based on reordering and ordering pattern. (Big picture)</li><li>Implement combine approach of department_id, aisle information based on reordering data(scatter plots)</li><li>Find out order conversion rate from add to cart data. (point plot)</li><li>Reorder ratio per hour and week for training dataset for finding best tie in week for selling during training period.</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3>Resultant Data Insights (Information achieved)</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Prior dataset is must large than train and test values.</li><li>Reordering products are between 4 to 100 times, means all purchased reorder products are ordered at least for 4 time or max 100 times</li><li>Customer buy most of product for 4 times (24000 around).</li><li>Weekly buying pattern shows the increase in weekend buying than week wording days. (least is on Wednesday)</li><li>Hourly pattern depict rush in daytime between 9:00AM to 6:00 PM.</li><li>In Prior data, best time for selling is Saturday afternoon (12 to 4)&nbsp; and Sunday morning (10 to 12)</li><li>Customer reordering frequency shows best pattern of buying weekly (7-day) and monthly(30-day) pattern for reordering rate.</li><li>59% order rows are reordered where 41% order sets are not.</li><li>But by product wise analysis&nbsp; 87% products were ordered again, and its good milestone for company.</li><li>Fresh fruits, vegetables and other milk items more frequently ordered than other.</li><li>Top 3 department in order contribution are produce, daily eggs and snacks.</li><li>Same trend in reordering pattern. (so we can assume constant market trend.)</li><li>In such department we can find the reordered aisle reordered ratio.</li><li>The best time of selling in training week is Tuesday and Wednesday morning (8 to 10) totally different from prior datasets.</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3><strong>Feature Creation:</strong></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Create user features set including size of user_id, product_id, all product’s total length and by calculating a average basket size respected to users.</li><li>User X product created by user’s last order with set including total number of orders, last order_id, and total sum of the cart. ( Create dictionary using looping)</li><li>On this dictionary did some basic operation of lambda function for order_id, total sum of order in cart up to data provided date.</li><li>Build candidate product list for reordering with some specific features ( useful only), such as order_id, user_id, length of orders length of user product list.</li><li>Create user related features such as order hour of day, day since prior order duration, ratio of such orders.</li><li>Calculate order ratio, last order id, average position of orders in cart, reorder rate, delta order hour (change in numbers since past)</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3>Model Training and Prediction:</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>Use LGB (light gbm (gradient boosting method) for problem since it is reinforced decision tree.</li><li> Train algorithm as per parameters with above generated features and test it &nbsp;with threshold value = 0.22 on predicted value set (test set).</li></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3>File Result:</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Prediction.csv</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Attachments:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/vedantdave77/PROJECT-Instkart_Market_Explotary-Analysis-and-LGB-ML-Modleing/blob/master/Instacart_Exploratory_Analysis_%26_Prediction_(LGB_ML_Algo_).ipynb">Code (Colab File)</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://drive.google.com/open?id=1407U2-rLP-crm2QFTSV55p3atR3neDsK">Data_set</a></strong></p>
<!-- /wp:paragraph -->
