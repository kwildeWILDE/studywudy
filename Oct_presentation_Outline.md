# Due by the end of October
## Presentation topic: A presentation to the MMSEI group on the overall CORSAIR dataset and some intresting weather/ wind evetns found in the dataset. 

##### Title Idea: 
    " The User Experience on Analysing High Winds from CORSAIR Instruments "

###### Why?: 
1. Here on the FC we have multiple remote sesnsing intrsuments that record atmopsheric characterists (i.e., tmeperature and wind), that we can asscess through the WDH (Wind Data Hub). 
2. The reson why we need to care about the atmospheric conditions is because the intensity and the behaviors of the atmospheric movement is important to know for wind turbines and researching about the correlation between power outages and extreme weather events 

###### What?:
1. The goal of this presentation is to show the methods and results I have devloped from analyzing multiple CORSAIR datasets. 
2. At the end of the presentation I hope that I get feedback on what I can do better in terms of looking through these datasets to help find extreme weather events impacting power and energy infrastruture.

##### How? 
1. As mentioned before the datasets are accessed through the NLR WDH from site 40's lidar and doppler radars and the dataset provided from the FC M2 met tower.
2. Pulling the dataset onto a python coding format (virtual studio) and create code that can format the pulled data into an xarray used for plot creation
3. So far the majority of the analysis I have done has only been for a single day (24-hour) period, but (maybe) in this presentation I can also show and example of multi-day atmospheric boundary layer analysis to show that these methods could also be used in a longer-term analysis.

###### The Cautions
1. It goes without saying that data analysis through remote sensing does have some of its faults.
2. From some of the examples I will later show, you will see examples of there being gaps in the data or some of the atmospheric characterisits will be poorly recorded.
3. This isn't to dismiss *all* of the remote sensing data, I am just going to show you what to be in the look out for and some methods and thought processes I have been using so far to determine what is good quality data and what is faulty. 
4. I will also show that there are some precautions that also need to be made when analyzing remote sensing CORSAIR data for a specific date (i.e., some of the recorded dates and times across the instruments might not exactly match up with eachother)

###### The Dataset Workflow
######      The M2 Met tower on the FC
1.  I personally like to start looking at the atmospheric charactersits from the M2 tower before looking at any CORSAIR data because of several reasons 
    (i) It has a boarder time period of recorded data so there's no need to worried if it can't correlate to the recorded time of the other CORSAIR datasets
    (ii) There are mutiple atmosphersheric charactersitics (temperature, wind, and Richardson Number) in the same dataset that can be used to create plots that can provide a "big picture" analyst of the atmospheric events happening at multiple heights. 
    (iii) However, it is NOT a perfect dataset and need to be cautious of poor data recording due to instrument malfunctioning (i.e., the 80m temperature reocordings for a few dates, and the period where the 2m and 5m wind directions were acting faulty as well)
        (a) However if spotted as soon as possible then it is possible to get it fixing in a reasonable time (dependet on the FC resources at the moment)
    (iv) another con is that there's not much of a "quality mask" variable on the datset so you will either have to use a different instrument's dataset to compare or use some meterological logic to make sure that the recorded data  from the M2 tower makes sense.

######  The s40.assist.tropoe CORSAIR dataset
2. The next dataset I like to look at after the M2 dataset is the s40.assist.tropoe, because the s40.assist.tropoe dataset primarily has temperature over heights and is a good tool to use to plot the temperature and thermodynamic profile over height at a specific time. It could also be used to compare the time-series of temperature from the M2 dataset to see if there is any agreement of disagreement between the two datasets (which is a good method to see if the temperature recording from the M2 tower is good quality)
    (i) A good feature of the s40.assist.tropoe dataset is that it comes with values that determine the "quality" of the data, which can be used to make a code that can create a "quality mask" and ignore the datapoints that go over the "quality mask" for plotting and data analysis reasons.
    (ii) However, from this quality mask method, when plotting the s40.assist.tropoe data, ther will be portions of the plot that will apprear blank or missing from he rest of the data, so the assisst.tropoe is a little dependent of the obeservation from the M2 data to fill in the blanks. 

###### The s40.lidars CORSAIR datasets
3. Thses dataset are primairly focused on the charactersitics of wind (speed and direction), but can provide as a good tool to compare to the M2 wind charactersitcs for agreement. 
    (i) However similarly to the s40.assist.tropoe dataset, it does come with a "data quality" variable that is good from only showing points of data that are "good quality" however can lead to ther being blanks and gaps when plotting
    (ii) With the use to the the M2 and the s40.lidar wind data you can figure out *when* excatly the highest wind speed event it happening, which could lead to the inversigation on *why* that high speed wind event is happening. 

###### The fc.ddoppler CORSAIR dataset
4. This dataset and tool can be used to create a 2D map (at verious heights) of the wind speed and direction happening at the FC at a certain time. 
    (i) This plot (along with the temperature/thermodynamic profile from the s40.assist.tropoe) is a best to do at the last step *after* finding the the exact time of a extreme wind event across all the analyzed datasets.

###### Example method and results to show: 
1. The September 19,2026 just M2 analysis
2. The April 12, 2026 compliation of datasets

###### Methods to find the Extreme (Intresting) Events 
1. M2's Richardson Number plottted as a time line
2. crating a bi-virate KDE gaussain contour line plot with the raw scatter data plotted as an over lay, and using the points that are outside of the KDE ellipises to indicate extreme/ low-probability events
    (i) Then along the timeline of the seprate bi-virate variable (i.e., temperature and wind speed) highlight the time *when* these low probability happened and see if they correlate to the low number on the richardson number time line.
3. When having the time corrdinate matching up between the M2 and the s40.lidar you can create a list of of when the highest windspeeds are happening at their respective heights and see if there is a match of high wind speeds at different heights happening at the same time. 

###### Discussion and Conclusion
1. When it comes to weather and atmospheric analysis, it is always a good rule of thumb to look at the datasets across diffent remote sensing instruments because they show agreement or "help eachother" out by either filling in the gaps of another dataset or expose the "poor quality" data of another (i.e., temperature between the M2 tower and the s40.assist.tropoe) 
2. However the biggest issue when it comes to analyzing atmospheric behavior between multiple remote sensing instruments is that some of them will have differnt "recording" periods or will have days worth of missing data when the other intruments have recorded data. So if you would want to ananlyze the atmosphere on a *specific* day you would have to look through the WDH or the .nc files log of your desired instrtruments to see if they all have some data on the day you want to analyze.
    (i) This could also lead to a conversation on how doing an observation over a range of days versus a single day might be more benificail to not have to worry as much about this issue. 
    (ii) Still, if there was some way to get access to a report of when certain instruments were offline or malfunctioning then it would be helpful to get an idea of of what to expect when it comes to plotting the data at a certain date and time.
3. I hope that the methods and resouces I talked about today give some insight and inspiration on methods we can use indicate extreme weather events that could cause issues to wind turbines and the power grid. 