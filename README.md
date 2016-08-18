```
                     ________                            
M               M   /_  __/ /  ___                       
M M           M M    / / / _ \/ -_)                      
M M M       M M M   /_/_/_//_/\__/         __        ____
M M M M   M M M M     /  |/  /__ ________ / /  ___ _/ / /
M M M M M M M M M    / /|_/ / _ `/ __(_-</ _ \/ _ `/ / /
M M M M M M M M M   /_/__/_/\_,_/_/ /___/_//_/\_,_/_/_/  
M M M M M M M M M     / _ \_______    (_)__ ____/ /_     
M M M M M M M M M    / ___/ __/ _ \  / / -_) __/ __/     
M M M M M M M M M   /_/  /_/  \___/_/ /\__/\__/\__/     
                                 |___/  
```

# The FBI's Uniform Crime Reporting Program
Is crime in America rising or falling? The answer is not nearly as simple as politicians make it out to be, because of how the FBI collects crime data from the country’s more than 18,000 police agencies. Even at their best, national estimates can be inconsistent and out of date, as the FBI takes months or years to piece together reports from those agencies that choose to participate in the voluntary program.

To try to fill this gap, The Marshall Project collected and analyzed more than 40 years of data on the most serious violent crimes in 68 police jurisdictions. We obtained 2015 reports, which have yet to be released by the FBI, directly from 61 of them. Our resulting analysis found that violent crime in these cities and counties rose 4 percent last year.

Our story, "[Crime in Context](https://www.themarshallproject.org/2016/08/18/crime-in-context)," was published by The Marshall Project on Aug. 18, 2016.

Included in this repo is the table of data The Marshall Project assembled and used to analyze and visualize the violent crime trends in these cities. If you'd like to use the data, found in ```data/ucr_crime_1975_2015.csv```, please read on for its genealogy and caveats about its limitations.

## Data sources and caveats

The Marshall Project compiled the most recent Uniform Crime Reporting numbers available on the four major crimes the FBI classifies as violent: homicide, rape, robbery and assault.

We collected information on the jurisdictions that are members of the Major Cities Chiefs Association, which collected violent crime numbers for 2015 and the first two quarters of this year. All but one of the members in the Major Cities Chiefs Association have populations of 250,000 or greater.

We found, however, that the respondents to the Major Cities Chiefs Association [survey](https://www.themarshallproject.org/documents/3023302-MCCA-Violent-Crime-Data-Midyear-2016-2015-8716) had many different ways of reporting the data that made it impossible to compare the chief’s numbers to FBI data we had already amassed from the the Uniform Crime Reporting program’s “Offenses Known and Clearances by Arrest” databases.

Unless noted otherwise, the source of each record (in the "source" column in the ```data/ucr_crime_1975_2015.csv```) is [the Uniform Crime Reporting program](https://www.icpsr.umich.edu/icpsrweb/NACJD/series/57)'s 'Offenses Known and Clearances by Arrest' database for the year in question, held at the National Archives of Criminal Justice Data.

To obtain 2015 reports before they are set to be published by the FBI later this year, we contacted the 68 different police agencies. We were unable to get 2015 data for seven: Baltimore County, Md., Cincinnati, Cleveland, Columbus, Ohio, Louisville, Ky., Portland, Ore., and Seattle.

The majority of the police agencies we chose are municipal departments, and for ease of phrasing, we collectively refer to our sample as cities. However, at least three agencies patrol both cities and counties — the Charlotte-Mecklenberg, N.C., Police Department; the Jacksonville, Fla., Sheriff’s Office; and the Louisville Metro Police Department. There are also eight departments whose jurisdictions include whole or parts of counties:
* Baltimore County Police Department
* Fairfax County, Va., Police Department
* Los Angeles County Sheriff’s Department
* Miami-Dade, Fla., Police Department
* Montgomery County, Md., Police Department
* Nassau County, N.Y., Police Department
* Prince George’s County, Md. Police Department
* Suffolk County, Md., Police Department

In some cases, the department or its state reporting agency had already published 2015 numbers using the FBI’s Uniform Crime Reporting summary reporting system. In several cases, we had to ask the department directly for the figures. Many had to convert the data from a newer, [incident-based system](https://ucr.fbi.gov/nibrs-overview) to the summary system.

For every department, we calculated the rate of crime in each category and for all violent crime, per 100,000 residents in the jurisdiction, based on the FBI’s estimated population for that year. For 2015, we used the 2014 estimated population.

The weighted average is a LOESS regression. The hierarchical cluster analysis uses Ward’s algorithm (“ward.D”) as implemented in the statistical analysis program R.

There are downsides to the Uniform Crime Reporting program. Differing counting methods, changing definitions of crimes, voluntary and sometimes erratic participation lead to data being slow to emerge to the public and often full of [holes and caveats](https://ucr.fbi.gov/ucr-statistics-their-proper-use). At any point in time, the most recent full-year numbers from the Uniform Crime Reporting program are between nine and 21 months old.

Wherever possible, we went back to individual states, the departments themselves or contemporary news accounts to fill in data missing from the databases. Still, there were four instances where we were unable to locate data:
* All four violent crimes for the Tampa, Fla., Police Department in 1988, a year in which Florida transitioned between counting systems, affecting many departments in the state.
* Aggravated assault for the Jacksonville Sheriff’s Office in 1988
* Rape figures for the Detroit Police Department in 1993
* All four categories for the Cincinnati Police Department in 1997 and 1998

Similarly, when we found that one of our chosen departments did not report crimes for all 12 months in a given year, we did our best to go back and find full-year counts. We were able to fill in many of the gaps, but there were some, particularly those more than 30 years ago, that we were unable to locate. All of our counts are for 12 months of reported crime, except for:
* New Orleans Police Department in 2005. The agency only reported for the first six months of the year and stopped after Hurricane Katrina hit the city.
* Indianapolis Police Department in 1995
* Omaha, Neb., Police Department in 1992
* Orlando, Fla., Police Department in 1991
* Tucson, Ariz., Police Department in 1989
* Suffolk County Police Department in 1975, 1981-1986 and 1988
* Prince George’s County Police Department in 1987
* Nassau County Police Department in 1983
* Houston Police Department in 1980 and 1981
* Buffalo, N.Y. Police Department in 1981
* Miami-Dade Police Department in 1975

In 2013, the FBI [changed how it defined rape](https://ucr.fbi.gov/crime-in-the-u.s/2013/crime-in-the-u.s.-2013/rape-addendum/rape_addendum_final). Until that point, rape was only counted if it was “carnal knowledge of a female forcibly and against her will.” The revised, broader definition became: “Penetration, no matter how slight, of the vagina or anus with any body part or object, or oral penetration by a sex organ of another person, without the consent of the victim.” This presented several challenges. In 2013 and 2014, as more cities began to adopt the definition, the number of reported rapes jumped. However, adoption of the revised definition has not yet been universal. Utah could only provide 2015 rape figures using the older definition. Other places had been using the more expansive definition for decades. The FBI had excluded Chicago’s rape figures from its annual reports because of the difference in definitions since 1984. To fill those gaps, we went back to the Chicago Police Department to collect the rape reports and add them to our data.

Finally, for the attack on the World Trade Center on Sept. 11, 2001, we removed 2,823 people from New York City’s 2001 homicide count, as advised in the Uniform Crime Reporting documentation for that year.

## Contributors

* Gabriel Dance, [The Marshall Project](https://www.themarshallproject.org/staff/gabriel-dance)
* Tom Meagher, [The Marshall Project](https://www.themarshallproject.org/staff/tom-meagher)
* Emily Hopkins, [The Marshall Project](https://www.themarshallproject.org/staff/emily-hopkins)

## Bugs
If you have questions about the data, please email Tom at ```tmeagher@themarshallproject.org``` or file a [Github issue](https://github.com/themarshallproject/city-crime/issues).
