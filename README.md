# wellness_automation

## The Tech

<div align="center">
	<code><img height="40" src="https://user-images.githubusercontent.com/25181517/183914128-3fc88b4a-4ac1-40e6-9443-9a30182379b7.png" alt="Jupyter Notebook" title="Jupyter Notebook" /></code>
	<code><img height="40" src="https://user-images.githubusercontent.com/25181517/183423507-c056a6f9-1ba8-4312-a350-19bcbc5a8697.png" alt="Python" title="Python" /></code>
</div>

## Purpose

When working at a Home Care Tech Startup I realised that our company was lacking the ability to gather its data into a coherent picture.
We had multiple apps that actively asked our Carers to record certain data points but in the early days of the company we did nothing with this information.
It occurred to me that if we could harness this data we could start delivering care from a pro-active angle, rather than reactive. Maybe we did not have to wait for people's conditon to deteriorate before taking action.

## How it works

1. Choose which file you want to read in as a csv.
2. As the data I had access to was messy the it is then automatically cleaned. Sorting it into the relevant headers of data points we want to look at and clearing out extra data that would create noise.
3. This is then assigned to a new Pandas Dataframe called client_names.
4. At this point all of the client data is still aggregated and we need to sort it into individual dataframes for presentation.
5. This is done by passing a Numpy array of client names into a function that sets the dataframe index and resamples the data to weekly data. I elected to resample the data to weekly because we are looking for long term health trends. Additionally, the data across all clients is not collected at the same intervals, some are once a week, some were three times a day. By refactoring to weekly we get the best holistic picture.
6. The plotting_keys function is then called taking all the unique client names, iterating over their aggregated data plotting it and saving the output to pdf.
