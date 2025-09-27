# Website-Performance-Analysis-EDA-Python-Project

This project focuses on analyzing website performance data to uncover key insights through Exploratory Data Analysis (EDA). Using Python libraries such as NumPy, Pandas, Matplotlib, and Seaborn, the project demonstrates how to clean, process, and visualize data for better decision-making.

# ✅ Objective 

The main goal of this project is to analyze and understand the performance of a website using Python. By leveraging key libraries like numpy, pandas, matplotlib, and seaborn, this analysis aims to explore user behavior, traffic patterns, and overall website efficiency. Through Exploratory Data Analysis (EDA), the project identifies trends, patterns, and anomalies to provide actionable insights that can improve user experience and optimize website functionality.

# 📂 Tools and Libraries Used

* Numpy – For numerical operations and handling large datasets efficiently.
* Pandas – For data manipulation, cleaning, and transformation.
* Matplotlib – For creating visualizations such as line charts, bar graphs, and histograms.
* Seaborn – For advanced statistical visualizations that highlight relationships between variables.
* Exploratory Data Analysis (EDA) – To uncover hidden patterns, understand distributions, and derive meaningful conclusions from raw data.

# Analysis :-

# 1.What patterns or trends can you observe in website sessions and users over time.

** plt.figure(figsize=(10,5))

df.groupby("DateHour")[["Sessions","Users"]].sum().plot(ax=plt.gca())

plt.title("Sessions & Used Over Time")

plt.xlabel("DateHour")

plt.ylabel("Count")

plt.savefig("sessions and used over time.png",dpi=2000,bbox_inches="tight")

plt.show() **

<img width="793" height="492" alt="image" src="https://github.com/user-attachments/assets/309fd46d-8796-4616-a79c-3cbb93e59aa3" />
<img width="17089" height="10116" alt="Sessions_And_Used_Over_Time" src="https://github.com/user-attachments/assets/319fe6fa-2ba0-48f3-93ff-e747b2a524e4" />

Insights for This visual
* Daily Trend: Both sessions and users show strong daily cycles, with high activity during peak hours and significant drops during late nights/early mornings.
* Sessions > Users: The sessions line is consistently above the users line, meaning users often initiate multiple sessions per day.
* Traffic Spikes: There are noticeable traffic surges (e.g., around mid-month), which could be linked to campaigns, promotions, or seasonal effects.
* Consistency: Despite fluctuations, the overall traffic pattern remains stable, showing steady engagement across the month.
* User Engagement: Since the gap between sessions and users is relatively constant, it suggests stable user behavior (returning users engaging multiple times).

# 2.Which marketing channel brought the highest number of users to the website,and how can we use this insight to improve traffic from other sources?

** Set figure size (width=5, height=4)
plt.figure(figsize=(5, 4))

 Create barplot showing total Users by channel group
- data=df → using dataset df
- x="channel group" → categories on x-axis
- y="Users" → values on y-axis
- estimator=np.sum → sum all Users for each channel
- palette="viridis" → color style
 < sns.barplot(data=df, x="channel group", y="Users", estimator=np.sum, palette="viridis") >

Add title to the chart
 < plt.title("Total User By Channel")>

Rotate x-axis labels for better readability
 < plt.xticks(rotation=45) >

Save plot as a high-resolution PNG file
< plt.savefig("total_user_by_channel.png", dpi=2000, bbox_inches="tight") >

Display the plot
 plt.show() **
<img width="860" height="556" alt="image" src="https://github.com/user-attachments/assets/39a13f98-4b35-4bd3-8156-a3bd73b5530c" />
<img width="483" height="467" alt="download" src="https://github.com/user-attachments/assets/7b94db26-76fc-4140-8b46-5543d07ec640" />

# Insights for This visual
* Highest Channel: The chart shows that Organic Social brought the highest number of users (nearly 48,000).
* Other Strong Channels: Direct traffic (~30,000 users), Organic Search (~28,000 users), and Referral (~27,000 users) are also major contributors.
* Low Performing Channels: Email, Organic Video, and Unassigned channels contribute very little traffic compared to the top sources.

# How to impact This insight
* Leverage Strength of Organic Social
* Since Organic Social drives the highest traffic, continue investing in social media campaigns, influencer partnerships, and consistent posting to maintain and grow this channel.
* Boost Underperforming Channels
* Explore targeted email campaigns (personalized offers, newsletters) to improve the Email channel.
* Enhance video marketing strategies (YouTube SEO, short-form videos, reels) to increase Organic Video performance.
* Optimize Search & Referral
* Strengthen SEO strategies (keyword optimization, content updates) to improve Organic Search further.
* Build more partnerships & backlinks to grow Referral traffic.
* Diversify Traffic Sources
* Don’t rely too heavily on one channel. By improving lower-performing channels, you reduce risk and create a balanced acquisition strategy.

# 3.Which channel has the highest average engagement time,and what dose that tell us about user behavior and content effectiveness?

** Set figure size (width=5, height=4)
plt.figure(figsize=(5, 4))

Create barplot showing Average Engagement Time per Session by channel group
- data=df → using dataset df
- x="channel group" → categories on x-axis
- y="Average engagement time per session" → values on y-axis
- palette="magma" → color style for the bars
< sns.barplot(
    data=df,
    x="channel group",
    y="Average engagement time per session",
    palette="magma"
) >

Add title to the chart
<plt.title("Average Engagement Time By Channel")>

Rotate x-axis labels for better readability
<plt.xticks(rotation=45)>

Save the plot as a high-resolution PNG file
<plt.savefig("avg_engagement_time_by_channel.png", dpi=2000, bbox_inches="tight")>

Display the plot
<plt.show() >**

<img width="854" height="667" alt="image" src="https://github.com/user-attachments/assets/138816d6-a72b-4869-9ecf-9c9052acdc53" />
<img width="466" height="467" alt="download" src="https://github.com/user-attachments/assets/c198e9eb-366b-4ace-a9fc-3591589db1fb" />

# Insights for This visual
* Highest Engagement – Organic Video
* Users from the Organic Video channel have the highest average engagement time (~180+), showing they spend significantly more time on the site compared to other channels.
* This indicates that video content is highly effective in keeping users engaged.
* Moderate Engagement – Referral & Unassigned
* Referral traffic (users coming from other websites) and Unassigned traffic show good engagement (70–90 range).
* These sources could be nurtured further with targeted content and partnerships.
* Lower Engagement – Direct, Organic Social, and Organic Search
* Direct visitors and Organic Search/Social users spend less time per session (~40–55).
* This suggests they may be looking for quick information or not finding enough engaging content.
* Email Channel – Inconsistent Engagement
* Engagement time from Email traffic shows high variation (large error bar).
* Some campaigns may perform well, while others fail to capture user attention → needs optimization in targeting and content.

# How to impact This insight
* Invest more in video content since it clearly drives the deepest engagement.
* Enhance on-site experience for Direct, Organic Social, and Organic Search visitors (better landing pages, interactive content).
* Optimize Email campaigns by testing subject lines, personalization, and segmentation to reduce variability.
* Strengthen referral partnerships to continue growing this moderately strong channel.

# 4.How does engagement rate vary across different traffic channels?

** Set figure size (width=8, height=5)
plt.figure(figsize=(8, 5))

 Create a boxplot to show engagement rate distribution by channel group
 - data=df → dataset being used
- x="channel group" → categories on x-axis
 - y="Engagement rate" → numerical values on y-axis
 - palette="coolwarm" → color style for boxplot
 sns.boxplot(
    data=df,
    x="channel group",
    y="Engagement rate",
    palette="coolwarm"
)

 Add chart title .
plt.title("Engagement Rate Distribution By Channel")

 Rotate x-axis labels for better readability.
 plt.xticks(rotation=45)

 Save the plot as a high-resolution PNG file .
plt.savefig("engagement_rate_distribution_by_channel.png", dpi=2000, bbox_inches="tight")

 Display the plot .
plt.show() **

<img width="872" height="676" alt="image" src="https://github.com/user-attachments/assets/8cbbe198-c3ea-41b6-9a6f-5d85e9432fbd" />
<img width="695" height="544" alt="download" src="https://github.com/user-attachments/assets/146451d3-a46d-4ab4-9123-d4e08598186f" />

# Insights for This visual
* Referral Shows the Highest Engagement
* Referral traffic has the highest median engagement rate (~0.6+) and a relatively tight spread, suggesting users coming from external sites are highly engaged and consistent.
* Organic Channels Perform Steadily
* Organic Social and Organic Search show strong median engagement (~0.5–0.6).
* Their distributions are relatively wide, meaning engagement varies depending on user intent or campaign quality.
* Direct Traffic
* Direct visitors have a slightly lower median engagement (~0.45) compared to Organic and Referral traffic.
* This indicates that while direct users are interested, they may not stay as engaged as those coming from targeted channels.
* Email Channel – High Variability
* Email shows a wide range of engagement rates, with some sessions at very low engagement and others at the maximum (1.0).
* This suggests email campaign performance is inconsistent — some campaigns resonate strongly, while others fail to engage.
* Unassigned & Organic Video
* These channels show little to no consistent engagement (flat or minimal distribution), meaning they currently do not contribute effectively to driving quality sessions.

# How to impact This insight
* Double down on Referral & Organic channels → they drive the most consistent engagement.
* Optimize Direct traffic → improve homepage or landing experiences to boost session depth.
* Refine Email campaigns → A/B test subject lines, personalization, and timing to reduce variability.
* Re-evaluate Organic Video & Unassigned → either improve content strategy or shift focus if ROI is too low.

# 5.Which channels are driving more engaged sessions compared to non-engaged ones and what strategies can improve engagement in underperforming channels?

** Step 1: Group data by channel group and calculate total Sessions & Engaged Sessions
session_df = (
    df.groupby("channel group")[["Sessions", "Engaged Sessions"]]
    .sum()
    .reset_index()
)

 Step 2: Calculate Non-engaged sessions (difference between total and engaged sessions)
session_df["Non_engaged"] = session_df["Sessions"] - session_df["Engaged Sessions"]

 Step 3: Reshape data using melt to prepare for visualization
 - id_vars="channel group" → keep channel group as identifier
 - value_vars=["Engaged Sessions", "Non_engaged"] → melt these into one column
session_df_melted = session_df.melt(
    id_vars="channel group",
    value_vars=["Engaged Sessions", "Non_engaged"]
)

 Step 4: Create barplot comparing Engaged vs Non-Engaged Sessions by channel group
plt.figure(figsize=(6, 4))
sns.barplot(
    data=session_df_melted,
    x="channel group",
    y="value",
    hue="variable"
)

 Step 5: Add title and rotate x-axis labels for readability
plt.title("Engaged VS Non-Engaged Sessions")
plt.xticks(rotation=45)

 Step 6: Save plot as high-resolution PNG
plt.savefig("engaged_vs_non_engaged_session.png", dpi=2000, bbox_inches="tight")

 Step 7: Display the plot
plt.show()** 

<img width="855" height="830" alt="image" src="https://github.com/user-attachments/assets/6f2ec739-9231-407a-b981-df5e8f519dc3" />
<img width="561" height="467" alt="download" src="https://github.com/user-attachments/assets/c93423e5-1bb6-4657-b00a-98b1af06b0f9" />

# Insights for This visual
* Organic Social
* Has the highest number of engaged sessions among all channels, indicating that social traffic is actively interacting with content.
* However, non-engaged sessions are also significant, meaning there’s still scope to improve targeting or content quality.
* Direct Traffic
* Non-engaged sessions are slightly higher than engaged sessions, suggesting many direct visitors leave without meaningful interaction.
* This could be due to poor landing page experience or users coming for one-off visits.
* Organic Search
* Shows a healthy balance, with engaged sessions greater than non-engaged.
* Indicates that search-driven users are genuinely interested and more likely to interact.
* Referral Traffic
* Strong engagement performance where engaged sessions are almost double non-engaged sessions.
* Suggests high-quality referral sources sending relevant traffic.
* Email
* Very low activity compared to other channels, possibly due to weak email campaigns or low open/click-through rates.
* Unassigned Traffic
* Minimal activity, may indicate untagged or misclassified traffic in tracking setup.

# Takeaways:
* Organic Social & Organic Search are the strongest engagement drivers.
* Direct traffic needs optimization (improve homepage/landing experience).
* Email channel underperforming → opportunity to revamp email strategy.
* Referral traffic shows strong engagement → consider building more partnerships.

# 6.At what hours of the day does each channel drive the most traffic?

** Group data by Hour and Channel Group, summing the number of sessions
- Use unstack() to pivot channel groups as columns and fill missing values with 0
heatmap_data = (
    df.groupby(["Hour", "channel group"])["Sessions"]
      .sum()
      .unstack()
      .fillna(0)
)

- Set figure size (width=10, height=6)
plt.figure(figsize=(10,6))

- Create a heatmap to visualize traffic by hour & channel group
sns.heatmap(
    data=heatmap_data,   # heatmap data
    linewidths=.5,       # add small lines between cells
    annot=True,          # show numbers inside cells
    fmt='.0f'            # format numbers as integers (no decimals)
)

- Add title and labels
plt.title("Traffic By Hour & Channel")
plt.xlabel("Channel Group")
plt.xticks(rotation=45)   # rotate x-axis labels for readability
plt.ylabel("Day of Hour")

- Save the heatmap as a high-resolution PNG file
plt.savefig("traffic by hour and channel.png", dpi=2000, bbox_inches="tight")

- Display the heatmap
plt.show() **

<img width="817" height="774" alt="image" src="https://github.com/user-attachments/assets/c0dad6ed-b12d-4fe3-9216-54ea7d916a1d" />
<img width="796" height="621" alt="download" src="https://github.com/user-attachments/assets/e2d9fc31-d092-419c-b92e-7eff2598797a" />

# Insights from Traffic by Hour & Channel Heatmap:
* Peak Traffic Hours
* The website sees the highest traffic between 17:00 – 22:00 (evening hours) across most channels.
* This suggests that users are more active after working hours, likely browsing or engaging in leisure activities.
* Best Performing Channel
* Organic Social consistently drives the largest volume of sessions throughout the day, peaking in the evenings.
* This indicates strong brand presence on social platforms and suggests focusing more on social media campaigns.
* Direct Traffic Behavior
* Direct traffic is steady across the day but shows significant spikes around night hours (20:00 – 23:00).
* This might be from returning or loyal users directly accessing the site.
* Organic Search
* Search-driven traffic peaks around midday to evening (11:00 – 20:00), indicating users often search during breaks or after work.
* Referral & Other Channels
* Referral traffic is moderate throughout the day but shows an uptick during late morning and evening hours.
* Channels like Email and Unassigned contribute very little, highlighting opportunities for improvement.
* Strategic Takeaway
* Marketing efforts (ads, email campaigns, promotions) should be timed for evening hours to maximize reach.
* Underperforming channels like Email and Organic Video should be revisited with better targeting or creative strategies.

# 7.Is there any correlation between high traffic (sessions) and high engagement rate over time?

<img width="711" height="809" alt="image" src="https://github.com/user-attachments/assets/f9b3c397-871f-428b-b1c3-8695047f2a81" />
<img width="857" height="524" alt="download" src="https://github.com/user-attachments/assets/7b2dd56c-fb99-4cdb-9811-9b3eb254e2c1" />

# Insights from Engagement Rate vs Sessions Over Time
* High Variability in Sessions
* The number of sessions shows significant fluctuations throughout the time period. This suggests that user visits are heavily influenced by specific days or events, possibly marketing campaigns or content updates.
* Consistent Engagement Rate
* Despite variations in session volume, the engagement rate remains relatively stable. This indicates that the quality of interactions stays consistent, regardless of how many users visit the site.
* No Direct Correlation
* The data suggests that an increase in sessions doesn’t necessarily lead to a higher engagement rate. This could point to casual visitors or temporary spikes that don't result in deeper interactions.
* Potential for Targeted Engagement Strategies
* Since engagement doesn’t spike with sessions, focusing on strategies like personalized content or improved user experience during high-traffic periods could boost overall engagement.
* Room for Growth
* The stable engagement rate presents an opportunity to experiment with content, navigation, or features to encourage users to engage more during peak session times.

# 📌 Conclusion

This project offers a comprehensive look into website performance, supported by data-driven approaches. The use of Python and its data science libraries enabled efficient data handling and insightful visualizations. The findings provide a solid foundation for making informed decisions to enhance website performance and user satisfaction.


