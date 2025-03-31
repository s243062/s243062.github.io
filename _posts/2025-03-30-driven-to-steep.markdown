---
layout: post
title: "Driven to Steal: The Rise, Fall, and Rise Again of Vehicle Thefts in San Francisco"
date: 2025-03-30 12:00:00 +0100
categories: jekyll update
authors:
    [
        "Tomasz Stępień (s243062)",
        "Mirka Katuscáková (s246259)",
        "Karolina Janyga (s243068)",
    ]
---

{% if page.authors %}

<p class="post-authors" style="margin-top: -10px">
<strong>Authors:</strong> {{ page.authors | join: ", " }}
</p>
{% endif %}

![Image showing warning plate in San Franciso saying: Prevent Theft: Remove Valuables Lock Your Car](/images/car-theft-plate.png)
<span style="font-size: 14px; color: gray;">_Signs warn tourists not to leave valuables in their cars near crooked Lombard Street in San Francisco on Wednesday, March 16, 2016._</span>
<span style="font-size: 12px; color: gray;">
_Source: Michael Short/Special To The Chronicle_  
 <a href="https://www.sfgate.com/crime/article/S-F-car-break-ins-up-31-percent-nearly-triple-6894503.php" target="_blank" style="color: gray; text-decoration: none;">
Read more
</a>
</span>

Although San Francisco’s overall crime rate has dropped to historic lows, vehicle theft has had a turbulent journey. From sharp declines fueled by tech, to spikes after a major prison policy shift, to a quiet takedown of international car theft rings — this story reveals how car theft in SF mirrors larger criminal justice trends.

![Graph showing vehicle theft trend over 21 years (2003 - 2024) in San Francisco](/images/vehicle-theft-trend-line-chart.png)
<span style="font-size: 14px; color: gray;">_Trends in vehicle thefts in San Francisco (2003–2024), showing a sharp decline after 2005, followed by fluctuations and a recent rise before dropping again in 2024._</span>
<span style="font-size: 12px; color: gray;">
_Source: Figure based on our internal analysis and data_  
 <a href="https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-Historical-2003/tmnf-yvry/about_data" target="_blank" style="color: gray; text-decoration: none;">
Get access to data
</a>
</span>

<span style="font-size: 20px">Timeline:</span>

-   **2006 – Technology Helps Reduce Car Theft**  
    Before 2006, car theft was one of the most common crimes in San Francisco. But that all started to change as new technologies and smarter law enforcement tactics took hold. By 2006, the number of car thefts had dropped significantly. Some of the key innovations that made this possible included:

    -   The use of “bait cars” with hidden cameras and GPS trackers to catch thieves in the act
    -   Automated license plate readers (ALPR) that helped police track stolen vehicles in real-time
    -   Cars with upgraded factory security systems, making it harder for thieves to break in or drive away

    ([East Bay Times, 2007](https://www-eastbaytimes-com.cdn.ampproject.org/v/s/www.eastbaytimes.com/2007/02/16/car-thefts-decrease-statewide/amp/?amp_gsa=1&amp_js_v=a9&usqp=mq331AQIUAKwASCAAgM%3D#amp_tf=From%20%251%24s&aoh=17430097887173&referrer=https%3A%2F%2Fwww.google.com&ampshare=https%3A%2F%2Fwww.eastbaytimes.com%2F2007%2F02%2F16%2Fcar-thefts-decrease-statewide%2F))

<div style="text-align: center; padding-top: 20px; width: 80%; margin: auto;">
    <h4>Vehicle Theft Hotspots Comparison in SF (2003–2024) </h4>
</div>

<div style="display: flex; justify-content: center; gap: 20px;">
    <!-- Left Heatmap -->
    <div style="text-align: center;">
        <label for="yearSelectLeft" style="font-weight: 600; font-size: 16px; color: #7c7b7b">Select Year:</label>
        <select id="yearSelectLeft" style="padding: 5px; font-size: 14px; margin-left: 10px; color:#7c7b7b"></select>
        <div style="margin-top: 10px;">
            <iframe id="mapFrameLeft" src="/assets/heatmaps/heatmap_2003.html" width="400px" height="600px" 
                style="border: 2px solid #A9A9A9; border-radius: 8px;"></iframe>
        </div>
    </div>
    <!-- Right Heatmap -->
    <div style="text-align: center;">
        <label for="yearSelectRight" style="font-weight: 600; font-size: 16px; color: #7c7b7b">Select Year:</label>
        <select id="yearSelectRight" style="padding: 5px; font-size: 14px; margin-left: 10px; color:#7c7b7b"></select>
        <div style="margin-top: 10px;">
            <iframe id="mapFrameRight" src="/assets/heatmaps/heatmap_2024.html" width="400px" height="600px"
                style="border: 2px solid #A9A9A9; border-radius: 8px;"></iframe>
        </div>
    </div>

</div>

<div style="text-align: center; margin-top: 10px; padding-bottom: 10px;">
    <span style="font-size: 14px; color: gray;">
        Heatmap comparison between vehicle theft hotspots in San Francisco between two years of your choice. Darker areas indicate higher concentrations of thefts.
    </span>
    <br>
    <span style="font-size: 12px; color: gray;">
        Source: Figure based on our internal analysis and data.
        <a href="https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-Historical-2003/tmnf-yvry/about_data" 
           target="_blank" style="color: gray; text-decoration: none;">
           Get access to data
        </a>
    </span>
</div>

<script>
    function populateDropdown(selectId, iframeId, defaultYear) {
        var select = document.getElementById(selectId);
        var iframe = document.getElementById(iframeId);

        for (var year = 2003; year <= 2024; year++) {
            var option = document.createElement("option");
            option.value = year;
            option.textContent = year;
            if (year === defaultYear) option.selected = true;
            select.appendChild(option);
        }

        // Set the iframe source to the default year
        iframe.src = "/assets/heatmaps/heatmap_" + defaultYear + ".html";

        select.addEventListener("change", function() {
            iframe.src = "/assets/heatmaps/heatmap_" + this.value + ".html";
        });
    }

    // Populate dropdowns with default years set to 2005 (left) and 2006 (right)
    populateDropdown("yearSelectLeft", "mapFrameLeft", 2005);
    populateDropdown("yearSelectRight", "mapFrameRight", 2006);
</script>

The implementation of bait car programs appears to have influenced the spatial distribution of vehicle thefts in San Francisco. As shown in the heatmaps, high-theft hotspots shifted noticeably after the policy introduction — suggesting that thieves may have altered their behavior in response to increased risk in previously targeted areas.

-   **2011 – The Rise**  
    In 2011, California implemented AB 109: Public Safety Realignment, a major reform that diverted lower-level offenders from state prisons to county jails — or, in many cases, no incarceration at all. This new legislation caused significant issues, including:

    -   Thousands of offenders being released or left unsupervised
    -   Counties struggling with overcrowded jails
    -   A dramatic increase in motor vehicle theft

    The **Public Policy Institute of California (PPIC)** ([PPIC, 2013](https://www.ppic.org/publication/public-safety-realignment-and-crime-rates-in-california/)) reported that the rise in thefts was directly tied to the realignment policies. This period marked the reversal of a long-term decline in car thefts, especially in urban centers like San Francisco.

-   **2016-2018 – Tackling the Surge in Car Theft**  
    Between 2016 and 2018, California took significant steps to curb the rising rates of car theft under Senate Bill 1743, also known as the Motor Vehicle Theft Prevention Act ([SB 1743, 2017/2018](https://staging.chp.ca.gov/siteassets/files/2017-motor-vehicle-theft-prevention-act-report.pdf)). The state's Foreign Export and Recovery (FEAR) teams ramped up their efforts, focusing on high-risk areas like the Bay Area.  
    The Northern FEAR Team, responsible for San Francisco and surrounding counties, deployed several key strategies to tackle the issue:

    -   Conducting export inspections at the Port of Oakland to intercept stolen vehicles bound for international markets
    -   Collaborating with other law enforcement agencies to carry out multi-agency sweeps targeting repeat offenders

    One of the most notable operations during this time was **Operation Cold Day**, a major crackdown on organized theft rings. In collaboration with the San Francisco Police Department and other agencies, the operation led to the recovery of stolen vehicles—including high-end models like a Lexus and a Mercedes—destined for overseas sale.

-   **2020–2022 – The Pandemic Crime Shift & the TikTok Effect**  
    While overall crime in San Francisco declined during the pandemic, car thefts surged, jumping approximately 42% from 2019 to 2022 ([Axios, 2023](https://www.axios.com/local/san-francisco/2023/03/21/san-francisco-car-thefts-overall-crime-trends)). Several key factors contributed to this increase:

    -   Reduced police presence – Pandemic-related constraints led to fewer traffic stops and patrols, creating more opportunities for car thieves ([SF Chronicle, 2021](https://www.sfchronicle.com/crime/article/This-is-how-the-pandemic-changed-crime-in-every-16107691.php)).
    -   Economic strain – Widespread financial hardship correlated with a rise in property crimes, including auto theft.
    -   The “Kia Boyz” trend – A viral TikTok challenge showed how to hotwire certain Kia and Hyundai models using a USB cable. This led to a wave of thefts nationwide, with San Francisco among the hardest-hit cities ([SFGate, 2023](https://www.sfgate.com/bayarea/article/here-s-kia-s-stolen-across-country-17865710.php)).

    By the end of 2022, vehicle thefts in San Francisco had reached their highest levels in nearly a decade, following a broader national trend ([NICB, 2022](https://www.nicb.org/news/news-releases/nicb-report-finds-vehicle-thefts-continue-skyrocket-many-areas-us#:~:text=DES%20PLAINES%2C%20Ill.%2C%20September,a%2017%25%20increase%20since%202019.)).

-   **2024 – Record Low Crime & Reform Efforts**  
    After years of fluctuations, San Francisco’s overall crime rate dropped to its lowest level in 23 years. Both violent and property crimes saw double-digit declines compared to 2023, with car burglaries and auto thefts among the most significant decreases ([NBC Bay Area, 2025](https://www.nbcbayarea.com/news/local/san-francisco-crime-rate-drop-lowest-level-stats/3754109/)). Several factors affected this shift:

    -   Major drop in car burglaries – Car break-ins fell by more than half, marking one of the sharpest declines in recent history.
    -   Police reform efforts – The SFPD implemented nearly all of the 272 reforms introduced in 2017, which officials say helped improve public trust and efficiency.
    -   Tech-assisted enforcement – Officers expanded their use of automated license plate readers and drones to deter and track auto theft.
    -   Stronger coordination – A better working relationship between SFPD and the district attorney’s office played a role in more effective policing strategies.

    By the end of 2024, San Francisco recorded its lowest homicide rate since the early 1960s, and overall crime rates returned to levels not seen since 2001. While challenges remain, officials credited a mix of proactive enforcement, technology, and long-term reform efforts for the decline.

<div style="display: flex; justify-content: center; gap: 20px; padding-top: 30px">
    <div style="text-align: center;">
        <iframe src="/assets/plots/sf_car_thefts_policies.html" width="1000px" height="600px"></iframe>
    </div>
</div>

<div style="text-align: center; margin-top: 10px;">
    <span style="font-size: 14px; color: gray;">
        A line graph showing vehicle theft trends in San Francisco in relation to policy changes over time.
    </span>
    <br>
    <span style="font-size: 12px; color: gray;">
        Source: Figure based on our internal analysis and data.
        <a href="https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-Historical-2003/tmnf-yvry/about_data" 
           target="_blank" style="color: gray; text-decoration: none;">
           Get access to data
        </a>
    </span>
</div>

San Francisco’s car theft trends have fluctuated over the past two decades, closely tied to technological advances, policy changes, and social influences. A major **tech-driven decline** began after 2006, as police used bait cars and automated license plate readers, making vehicle theft riskier. However, in **2011, AB 109** prison reform led to an increase in thefts, as more offenders were released.

Efforts to counter the surge came in **2016 with FEAR operations**, targeting organized theft rings and international smuggling networks. Yet, in **2022, the TikTok Trend** triggered another spike, as viral videos revealed security flaws in certain car models, leading to a nationwide wave of thefts.

By **2024, SFPD reforms** helped bring crime rates to historic lows, using smarter enforcement tactics and improved police coordination.

Car theft in San Francisco has been a constant cycle of ups and downs, shaped by new laws, tech advancements, and even internet trends. The lesson? Crime doesn’t just disappear—it changes, finding new ways to adapt to the system.
