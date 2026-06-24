previous knowledge:- previous knowledge:- [[00 Introduction]], [[01 Distribution Plot]], [[02 Joint Plot]], [[03 KDE PLOT]], [[04 Pair Plot]], [[05 Rug plots]], [[06 Styling]], [[07 Categorical plots]], [[08 Heatmaps]]
A clustermap is basically a heatmap that automatically groups similar rows and columns together.
Heatmap + automatic clustering = Clustermaps
Its hard to sport patterns immediately in a heatmap.
![[Screenshot 2026-06-24 at 9.10.09 PM.png|361]]
Take this as an example where x and y are similar and z and w are similar. 
If this is randomly generated and x and y are at random places. cluster map will notice patterns on its own and arrange them accordingly. 

Basic syntax:- `sns.clustermap(df.corr())`
or `sns.clustermap(pivot_table,cmap='coolwarm, standard_scale = 1')`

example:- Lets take our flight example and understand it in depth. 
`plt.figure(figsize=(8,6))`
`sns.set_context('paper', font_scale=1.4)`
`flights = flights.pivot_table(index='month', columns='year', values='passengers')`
`sns.clustermap(flights,cmap="Blues", standard_scale=1)`
![[Screenshot 2026-06-24 at 9.17.03 PM.png|567]]
Here as u can see the months and years have been rearranged according to correlations. Whatever is more related is closer. like feb, jan and november together because they share a trend. july and august are together because most people travel in those months. The lines u see on top and left are called dendrograms and they connect to show which row and column is more correlated with each other in depth. 