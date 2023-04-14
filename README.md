# Water analysis

Author: Alex T

Date: March 15, 2023

Tools used: postgreSQL pgadmin4, Tableau public desktop


### Scenario

I came accross an interesting data of water quality. It includes chemicals and testing indexes that will be used to determine the quality of the water.

* pH: A quantitative measurement for acidity or basicity of a liquid form. It ranges from 0 to 14, with 0 being most acidic and 14 most basic. pH is not regulated by EPA as pH is a aesthetic feature, therefore subjective to people. However I found a fun fact from a UCLA Health article that says Human blood is 7.4!  I attached a picture below so we can put pH under some perspectives for easier comparison.


<img width="550" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/225225786-bf020060-1b32-438b-a6f1-d1229f2d774e.png">

* Hardness: Essentially is how high the mineral content in water is, the higher the content, the "harder" the water. Hardness has two categories: permanent and temporary hardness. Temporary hardness can be caused by Bicarbonates of Magnesium and Calcium. Some hardness can give moderate health benefits, others, however, can block oil pipeline leading to production loss. The range of hardness include soft, moderately hard, hard, and very hard. 

  - Soft: 0 to 60 mg/L

  - Moderately hard: 61 to 120 mg/L

  - Hard: 121 to 180 mg/L

  - Very hard: > 180 mg/L


Unit in our data is mg/L or ppm.

* Solids: (also as known as Total Dissolved Solids TDS) refers to the dissolved substances in water. These substances contain inorganic and organic matters that may cause harm for consumption. Typically solids presence cannot vaporize, instead can be physically removed by a filter. Since TDS is not a measurement of any single element or material, but a combination of them, TDS affects taste and odor of the water, and EPA doesn't regulate this index, however, has suggested the safest maximum for consumption is 500mg/L. (3) Unit in this data is mg/L or ppm.

* Chloramine: is a type of disinfectant used to treat water from bacteria as well as waterborne diseases in water pipeline. Formed when combined chlorine with ammonia. An usual amount of chloramine used is between 1.0 and 4.0 mg/L. No health effects related to chloramine has been reported with concentration under 50 mg/L (4). Unit in data: mg/L or ppm.


<img width="220" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/228851031-21cf15c9-b504-4a11-a9c2-c8aaddeebaa7.png">  <img width="700" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/225251682-e77ae47b-5df1-4a87-a83d-47528f5451fc.png"> 


* Sulfate: Higher than 500 mg/L sulfate in drinking water can lead to dehydration and laxative effect, especially in infants. Sulfate in drinking water can form sulfate-oxidizing bacteria, however, does not cause any known harmful effects to consumers (5).  Unit in our data is mg/L or ppm.

* Conductivity: Since there are dissolved salts and inorganic matters present in water, water has ability to conduct electrical current, the higher the salinity (higher ions), the higher the conductivity. After a period of pumping high saline water, not only household plumbing can be caused buildup but also there are health risks involved. There is no law passed for what conductivity in water should be, however the Environmental Protection Agency (EPA) recommend drinking water should have less than 1000 microsiemens per centimeter (mcg/cm) (6). The unit in our data is also mcg/cm.

* Organic carbon: Naturally organic carbons are present in water sources. Depends on how filtered and processed the water is, organic carbon or total organic carbon (TOC) is measured using analytical equipments. Unit in our data is mg/L or ppm

<img width="400" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/228463271-7cbffbfd-0edd-4342-94d2-f34aac5fcc66.png">
(7)

* Trihalomethanes (THMs): THMs are the compounds that are formed when halogen elements replace hydrogen atoms. Trihalomethanes are often used as solvents or refrigerants. These compounds can cause cancer, especially colon, rectal cancers, and reproductive risks. The US EPA allows 100 parts per billion (ppb) in drinking water

<img width="800" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/228473721-3180a097-9b80-42c0-857d-7cbb5f5692b9.png">
(8)

* Turbidity: Is a measurement of water clarity by measuring the amount of light could be shined through scattered materials in water. The less light can be shined through, the higher the turbidity (9). Unit is in NTU. According to WHO, drinking water should be less than 1 NTU (11)

<img width="700" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/228488689-93cba48d-0bd1-452b-b406-87c01f20d770.png">
(10)

* Potability: Whether the water is drinkable or not. 1 for yes and 0 for no. 

Sources:

[1](https://www.uclahealth.org/news/ask-the-doctors-is-water-with-a-high-ph-safe-to-drink/)
[2](https://www.usgs.gov/special-topics/water-science-school/science/hardness-water/)
[3](https://www.kent.co.in/blog/what-are-total-dissolved-solids-tds-how-to-reduce-them/)
[4](https://www.cdc.gov/healthywater/drinking/public/water_disinfection.html#:~:text=Studies%20indicate%20that%20using%20or,protection%20against%20waterborne%20disease%20outbreaks/)
[5](https://portal.ct.gov/-/media/Departments-and-Agencies/DPH/dph/environmental_health/pdf/HydrogenSulfideSulfateinPDWWpdf.pdf/)
[6](https://www.epa.gov/national-aquatic-resource-surveys/indicators-conductivity#:~:text=What%20is%20conductivity%3F,conductivity%20increases%20as%20salinity%20increases/)
[7](https://www.elgalabwater.com/blog/total-organic-carbon-toc#:~:text=Total%20Organic%20Carbon%20(TOC)%20is,solution%20is%20for%20their%20processes/)
[8](https://www.valleywater.org/your-water/water-quality/how-we-clean-your-water/trihalomethanes-thms#:~:text=In%201979%2C%20the%20U.S.%20Environmental,parts%20per%20billion%20(ppb)/)
[9](https://www.usgs.gov/special-topics/water-science-school/science/turbidity-and-water#:~:text=Turbidity%20is%20the%20measure%20of,light%2C%20the%20higher%20the%20turbidity./)
[10](https://www.hyperfilteration.in/blogs/2022/04/08/what-is-turbidity/)
[11](https://www.lenntech.com/turbidity.htm/)

### Ask
* How many water entries are potable?
* How many water entries are in water hardness categories?
* How many water entries that has more than 500ppm solids?
* How many water entries that has more than 50ppm chloramine?
* How many water entries that has more than 500ppm sulfate?
* How many water entries that has more than 1000 mcg/cm conductivity?
* How many water entries that has more than 2ppm TOC?
* How many water entries that has more than 100ppb THMs?
* How many water entries that has more than 1 NTU in turbidity?
* How many water entries are drinkable and do these entries match with our own researched standards?

### Prepare
>   
    CREATE TABLE IF NOT EXISTS public.water(
    ph numeric,
    hardness numeric,
    solids numeric,
    chloramines numeric,
    sulfate numeric,
    conductivity numeric,
    toc numeric,
    thm numeric,
    turbidity numeric,
    potability boolean
    );
    
>   
    select * from water
    
Table was imported and looks good!

### Process

Look for duplicates: 
>   
    select count(*) from water
    where ph is not null
    and hardness is not null
    and solids is not null
    and chloramines is not null
    and sulfate is not null
    and conductivity is not null
    and toc is not null
    and thm is not null
    and turbidity is not null
    group by ph, hardness, solids, chloramines,sulfate,
    conductivity,
    toc,
    thm,
    turbidity
    having count(*) > 1;
    
Results shows none so I move on to finding missing values

> 
    select count(*) from water where ph is null
    
After plugging in the same syntax for all columns I found that there are 491 missing values in ph column, 781 in sulfate, 162 in THMs

### Analyze

First I want to look at the statistic summary of my dataset so I create a table of this summary

>
    create table summary_water as
    select 'ph' as category,
    round(avg(ph)) as mean,
    round(max(ph)) as max,
    round(min(ph)) as min,
    round(percentile_cont(0.5) within group
        (order by ph)) as median,
    count(ph) as count_total
    from water;

    select * from summary_water;

    select round(ph),count(round(ph))
    from water
    group by round(ph)
    order by count(round(ph)) DESC limit 1;


    select * from summary_water,

    insert into summary_water(category)
    values 
    ('solids'),
    ('chloramines'),
    ('sulfate'),
    ('conductivity'),
    ('toc'),
    ('thm'),
    ('turbidity'),
    ('potability')

    select * from summary_water;



    update summary_water
    set max = 
    (select round(max(hardness)) 
    from water),
    min = (select round(min(hardness))
         from water),
    median = (select round(percentile_cont(0.5)
        within group (order by hardness)) 
         from water),
    count_not_null = (select count(hardness)
        from water
        where hardness is not null),
    count_total = (select count(*) from water),
    count_null = (select count(hardness)
        from water
        where hardness is null)
    where category = 'hardness'

<img width="958" alt="Screenshot 2023-04-01 at 6 12 20 PM" src="https://user-images.githubusercontent.com/74520739/229285447-2d7e772a-fb98-4bc8-8b06-740bd4a9d32b.png">



I also found from "potability" column that there 1278 water entries that are considered drinkable, 1998 are not drinkable with no missing values. 


>
    select
    sum(case 
        when hardness < 61 then 1
        else 0
        end) "soft",
    sum(case
      when hardness >= 61 
        and hardness < 120 then 1
        else 0
        end) 
        as moderately_hard,
    sum(case
      when hardness >= 121 
        and hardness < 180 then 1
        else 0
        end) as hard,
    sum(case
      when hardness > 180 then 1
      else 0
      end) as very_hard
    from water;

Results show 1 water is soft, 51 waters are moderately_hard, 878 waters are hard, and 2341 waters are in very hard category. 

> 
    select count(solids) from water
    where solids > 500;  

There are 3275/3276 waters have over 500ppm solids.

>
    select count(chloramines) from water
    where chloramines <50
    
There are 3276/3276 water returns to be under 50ppm chloramines.

>
    select count(sulfate) from water
    where sulfate <500;
    
There are 2495/2495 sulfate concentration under 500ppm so 0 are more than 500ppm

>
    select count(conductivity) from water
    where conductivity <1000;

There are 3276/3276 water returns to be under 1000mcg/cm so 0 are more than 1000mcg/cm in conductivity

>
    select count(toc) from water
    where toc >2;

There are 3276/3276 water returns to be above 2ppm total organic carbon.

> 
    select count(thm) from water
    where thm > 100;
    
There are 60/3114 entries return to be above 100ppb trihalomethanes.

>
    select count(turbidity) from water
    where turbidity > 1

There are 3276/3276 water entries return to be above 1 NTU in turbidity.

    
### Share

<img width="750" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/232004974-3c5db91c-7d5d-460b-9d7c-5742c85fd24b.png">


<img width="750" alt="2023-03-015_10000" src="https://user-images.githubusercontent.com/74520739/232005971-abaf09a2-7ef1-4c4d-9b83-fdc211d9de52.png">


### Act

According to my research, drinkable water should have a maximum turbidity of 1NTU. From the datasets, there are 3276/3276 waters that have more than 1 NTU turbidity. That means the water is not clear enough for drinking according to WHO suggested standard. However, the potability data suggests 1278 waters that are considered drinkable. From this data alone, we can already conclude that our researched potability does not match the one in the datasets. Same results shown in total organic carbon concentration. A suggested concentration of 2ppm is considered safe to consume, but all data entries do not pass this criteria.

Say we let the turbidity and total organic carbon aside, trihalomethanes are carcinogenic and therefore no more than 100ppb of its concentration should be consumed. Based on what I found, 60/3114 waters have more than 100ppb trihalomethanes. Hence 3054 waters are drinkable based on trihalomethanes standard.

All waters pass 1000mcg/cm in conductivity and all water pass the criteria of 500ppm sulfate, and 50ppm in chloramines. 

There is only one water that pass a 500ppm standard for solids. 


