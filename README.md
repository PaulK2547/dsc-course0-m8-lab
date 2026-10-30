# Project Overview
The primary objective was to identify aircraft makes and models that demonstrate lower rates of total destruction and low likelihood of fatal or serious passenger injuries in the event of an accident. The client was interested in professionaly made airplanes that are potentially still actine. Additionally the cient sought recomendations for small vs large aircraft models.



# Data Filtering
The following columns were selected to provide the neccessary information requested by the client with various data cleaning procedures undertaken
1. Event.Date- Will assist to restrict the analysis to aircraft potentially still in service
2. Make/Model-Aircraft recommendations will be based on manufacturer and model
3. Amateur.Built- Client only wants professionally manufactured aircraft
4. Aircraft.Category-Focus on airplanes and exclude helicopters, balloons, gliders, etc.
5. Aircraft.damage-To capture the extent of the damage
6. Injury.Severity, Total.Fatal.Injuries,Total.Serious.Injuries and Total.Uninjured - Will assist in assesing passenger survivability
7. FAR.Description-Helps identify commercial operations
8. Purpose.of.flight-Can distinguish personal vs professional use

# New columns added
To better measure safety outcomes, several new variables were created:
1. Total Passengers=Total.Fatal.Injuries+Total.Serious.Injuries+Total.Minor.Injuries+Total.Uninjured
2. fatal.serious.injuries=Total.Fatal.Injuries+Total.Serious.Injuries
3. fatal.seriuos.rate=fatal.serious.injuries/Total.Passengers
4. damage.score - This was based on the average damage score from 0-4
5. Plane_Type- combined make and model to create a unique airplane identifier

# Other colums
Data cleaning procedures under taken for other columns. The list of other columns included: 
- Engine.Type
- Weather.Condition
- Number.of.Engines
- Purpose.of.flight
- Broad.phase.of.flight

# Combine new columns and other columns into the initially selected columns
The new and other columns were combined into the initially selected columns (df-clean)
The data was inspected and missing rows and columns dropped.

# Saved the cleanee dataframe into CSV (cleaned_aviation_data.csv')

# Data visualization
1. Fisrt, I created aircraft size groups ie small and large
2. Analysed injury rsk profile by aircraft size
3. Generated a plot for lowest injury rates for small and large aircrafts
4. I evaluated the rate of aircraft destruction for both small and large aircraft by Make
5. I combined injury risk and damage severity to provide a recommendation for Makes bsed on these two metrics
6. Analysed plane types on the same metrics but filtered only planes with atleast 10 accidents for both small and large aircrafts. This did not yield results. So I filtered by plane types with atleast 3 accident records. I found out that Large aircraft types generally tend to exhibit lower fatal/serious injury fractions while Small aircraft types typically show greater variation in injury outcomes than larger aircraft.
7. I explored other variables i.e weather conditions an Engine types. I found out the following. 
- Poor visibility and adverse weather are often associated with a greater likelihood of severe injuries and aircraft damage.
- Turbo Jet and Turbo Fan engines are the safest. They have a low mean fatal/serious injury fractions and low average damage scores.

