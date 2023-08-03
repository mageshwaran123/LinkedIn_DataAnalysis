# LinkedIn_DataAnalysis

# 1. Connection Growth Over Time:

Load Data: The code loads connection data from the CSV file "Connection_Data.csv" into a pandas DataFrame named df.

Data Preprocessing: It converts the 'Connected On' column to a pandas datetime object using pd.to_datetime, allowing easier manipulation of date-related operations.

Group Data: The code groups the data by month and counts the number of connections made each month. The results are stored in a new DataFrame called connections_per_month.

Create Interactive Bar Chart: Using Plotly Express (px.bar), the code creates an interactive bar chart. The x-axis represents the months, the y-axis shows the number of connections, and the chart is labeled and titled appropriately.

Customize Appearance: The color of the bars is set to blue using fig.update_traces().

Display and Save: The interactive chart is displayed using fig.show(), and it is saved as an HTML file named "connection_growth_chart.html" using fig.write_html().

# 2. Line graph - Historical data and Forecasted Growth of Connections Over Time using ARIMA Model - Next 12 Months

ARIMA Model Fitting: The code fits an ARIMA model to the historical connection counts using the ARIMA function from statsmodels.api. The order of the ARIMA model is set as (1, 1, 1) in this case.

Forecasting: ARIMA results are used to make predictions for the next 12 months using arima_results.forecast(steps=forecast_steps).

Create Forecast DataFrame: A DataFrame named forecast_df is created to hold the forecasted values and corresponding dates.

Combine Data: The historical data and forecasted data are combined into a single DataFrame named combined_df using pd.concat.

Create Line Graph: Using Plotly's graph_objects (go.Figure), a line graph is created. Historical data is plotted as a line with markers, and the forecasted values are plotted with another line.

Customize Appearance: The plot's title, x-axis, and y-axis labels are set using update_layout. Legend and axis types are configured as well.

Display and Save: The interactive line graph is displayed using fig.show(), and it is saved as an HTML file named "Forecasted_Growth_ConnectionsOver_Time.html" using fig.write_html()

Visualizes the distribution of the top companies and positions using a treemap

Convert to Long Format: The pivot table is converted to a long-format DataFrame using pd.melt. This transformation allows easier handling of data for plotting.

Sort Data: The DataFrame is sorted in descending order based on the count of individuals in each company-position combination using sort_values.

Create Treemap: Using Plotly Express (px.treemap), the code creates a treemap visualization. The treemap represents the top 100 companies and positions based on the sorted DataFrame. The size of each rectangle in the treemap corresponds to the number of individuals in that specific company-position combination.

# 3. Visualizes the distribution of the top positions and their associated companies using a treemap

Sort Data: The DataFrame is sorted in descending order based on the count of individuals in each position-company combination using sort_values.

Create Treemap: Using Plotly Express (px.treemap), the code creates a treemap visualization. The treemap represents the top 100 positions and their associated companies based on the sorted DataFrame. The size of each rectangle in the treemap corresponds to the number of individuals in that specific position-company combination.

Customize Appearance: The treemap's title and labels are set using labels and title parameters.

Display and Save: The interactive treemap is displayed using fig.show(), and it is saved as an HTML file named "Distribution_of_top_positions.html" using fig.write_html().

# Network Analysis:

Install igraph: The code installs the igraph library using the !pip install command.

Load Data: The code loads connection data from the CSV file "Connection_Data.csv" into a pandas DataFrame named df.

Create an Empty Graph: An empty graph G is created using igraph.Graph().

Add Nodes: Companies are added as nodes to the graph using their unique names extracted from the 'Company' column in the DataFrame.

Create Edges: Edges (connections) are created between companies that share at least one position. A nested loop iterates through unique company pairs, and if they share positions, an edge is added to the graph.

Generate Communities: The communities in the graph are obtained using the community_edge_betweenness function.

Set Attributes for Nodes: Graph nodes are positioned using the Kamada-Kawai layout. Node size is set, and each community is compressed into a single, "composite" vertex.

Set Colors for Clusters: Each community is assigned a unique color, and edges within each community are colored accordingly.

Get Top Companies: The code determines the top 30 companies based on their appearance frequency in communities.

Plot the Graph: The community network plot is created using ig.plot. Companies are represented by nodes with different colors corresponding to their communities. The legend displays the top 10 companies with their respective colors.

Display the Plot: The plot is displayed using plt.show().
