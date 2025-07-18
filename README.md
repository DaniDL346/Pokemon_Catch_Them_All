
# Pokemon Catch Them All!

**Pokemon Catch Them All!** is a comprehensive data analysis tool designed to streamline data exploration, analysis, and visualisation of a Pokemon tournament between two players with various types of Pokemon. The tool supports multiple data formats and provides an intuitive interface for both novice and expert data scientists.

<img src="https://static.wikia.nocookie.net/pokemon/images/0/01/0175Togepi.png" width="100" height="100" /> 


## Dataset Content
* The Kaggle dataset called \"Pokemon with stats\" and \"Pokemon- Weedle's Cave\", was used as raw data and saved under the "/Dataset/raw" folder under, [\"Pokemon with Stats\" for \"pokemon\"]( https://www.kaggle.com/datasets/abcsds/pokemon/data) and [\"Pokemon- Weedle's Cave\" for \"combats\"]( https://www.kaggle.com/datasets/terminus7/pokemon-challenge?select=pokemon.csv).
* The size of the raw files are 581KB for "combats.csv" and 44KB for "pokemon.csv".
* The column names are as follows:
    * \#: ID for each pokemon
    * Name: Name of each pokemon
    * Type 1: Each pokemon has a type, this determines weakness/resistance to attacks
    * Type 2: Some pokemon are dual type and have 2
    * Total: Sum of all stats that come after this, a general guide to how strong a pokemon is
    * HP: Hit points, or health, defines how much damage a pokemon can withstand before fainting
    * Attack: The base modifier for normal attacks (e.g. Scratch, Punch)
    * Defense: The base damage resistance against normal attacks
    * SP Atk: Special attack, the base modifier for special attacks (e.g. fire blast, bubble beam)
    * SP Def: The base damage resistance against special attacks
    * Speed: Determines which pokemon attacks first each round


       


## Business Requirements
The business requirements for this project are:

1. **Determine the Strongest Pokemon:** Identify which Pokemon have the highest overall stats and are most likely to win in tournament battles.
2. **Analyze Type Effectiveness:** Explore how different Pokemon types (Type 1 and Type 2) influence battle outcomes and identify any type advantages.
3. **Player Performance Comparison:** Compare the performance of the two players in the tournament based on their chosen Pokemon and battle results.
4. **Visualize Key Stats:** Provide clear visualizations of important attributes such as HP, Attack, Defense, Speed, and their impact on battle outcomes.
5. **Predict Battle Outcomes:** Use the dataset to build simple predictive models or rules to forecast the winner of a match based on Pokemon stats and types.
6. **User-Friendly Insights:** Present findings in a way that is accessible to both technical and non-technical users, supporting decision-making for future tournaments.


## Hypothesis and how to validate?
1. **Determine the Strongest Pokemon:** Identify which Pokemon have the highest overall stats and are most likely to win in tournament battles.
    * Visualisations were carried out in the "ETL_postprocessing and Visualisations" folder. A plotly bar chart was produced to view which Pokemon has the highest total power. The total power is calculated based on the addition of all the other characteristics that each type has.

    ![Total Power by Type 1](static_images/total_power_by_type_1.png)  
    
    * A correlation matrix highlighted each characteristic type.

    ![Correlation_Matrix](static_images/corr_matrix.png) 

    * In the Power BI Dashboard "Pokemon_Dashboard.pbix, visualisations were also plotted of the combined data of the tables "combats.csv" and "pokemon_cleaned.csv" to provide statistics on the winning Pokemon.

    ![Dashboard overview](static_images/Dashboard_cover.jpeg) 

2. **Analyze Type Effectiveness:** Explore how different Pokemon types influence battle outcomes and identify any type advantages.
    * Investigations were conducted in the Pokemon Power BI Dashboard highlighting Player 1(Type 1) vs Player 2(Type 1) advantages over the other as well as their strategies. You will find this in page 2 under "Player strategy" and page 3 and 4 under "Player 1 Statistics" and "Player 2 Statistics".

    ![Dashboard page 2](static_images/Dashboard_page2.jpeg) 

    ![Dashboard page 3](static_images/Dashboard_page3.jpeg)  

    ![Dashboard page 4](static_images/Dashboard_page4.jpeg)

3. **Player Performance Comparison:** Compare the performance of the two players in the tournament based on their chosen Pokemon and battle results.
    * The Pokemon Dashboard has a comparison of the statistics between the two players. The overview page, gives a brief overview of how many wins and losses both players achieved. The "Player Strategy" and "Player 1 Statistics" and "Player 2 Statistics" give an indepth view on how each player performed.

4. **Visualize Key Stats:** Provide clear visualizations of important attributes such as HP, Attack, Defense, Speed, and their impact on battle outcomes.
    * The Pokemon Dashboard provides information on pages 3 and 4 of the Dashboard indicating this important information for each player.

5. **Predict Battle Outcomes:** Use the dataset to build simple predictive models or rules to forecast the winner of a match based on Pokemon stats and types.
    * This section is answered in page 5 of the Pokemon Dashboard named "Predictive Model". It can be used to make forecasts and predict who will be the winner based on Pokemon types and characteristics.

6. **User-Friendly Insights:** Present findings in a way that is accessible to both technical and non-technical users, supporting decision-making for future tournaments.
    * The Jupyter notebooks named "ETL_Postprocessing and Visualisations", "Statistical_testing" and "Machine_learning_model" are for the technical audience and the Pokemon Dashboard is for a non-technical audience.

## Project Plan
* Outline the high-level steps taken for the analysis.
    * ETL - This section was used to extract, clean, transform and load the two datasets - "pokemon.csv" and "combats.csv".
    * ETL Post-processing and Visualisations - This section was used to create advanced visualisations based on the "pokemon_cleaned.csv". This section was used to join two tables to create the "combined_ml.csv" which is for the battle information on player 1 and player 2. This dataset was fed into the Machine Learning Model.
    * Statistical Testing - This provided more insights into the various data distributions if they were significantly different or not.
    * Machine Learning Model - In this notebook, a Grid Search CV method was used to compare the best Machine Learning Model that a prediction could be made on that provides the highest accuracy. In this section, the Hyperparameters were also adjusted to increase the accuraxy of the Machine learning Model.
    * Pokemon Power BI Dashboard - These visualisations are based on the "combined_ml.csv" to created visualisations and a predictive model for a non-technical audience. The visuals are created to be interactive. Each page aimed at looking into a particular area about the tournament and players statistics.
* How was the data managed throughout the collection, processing, analysis and interpretation steps?
    * The raw data "pokemon.csv" and "combats.csv" was loaded and cleaned, removing duplicates, unnecessary columns, managing outliers and producing basic plots to understand the data spread and distribution.
    * The cleaned data was stored into a folder called /Dataset/cleaned/ named "pokemon_cleaned.csv" and "combats_cleaned.csv". This was used to do a left join twice of the two tables to combine them and provide statistics for both player 1 and player 2.
    * The combined table was saved as "combined_ml.csv" and used in the Machine Learning Model, Statistical Testing notebook and the Pokemon Dashboard in Power BI.

* Why did you choose the research methodologies you used?
    * This provided me with a structed and organised way to perform the ETL, visualisations, Machine Learning Model and Statistical Testing on cleaned data.


## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

    1. **Determine the Strongest Pokemon:** Identify which Pokemon have the highest overall stats and are most likely to win in tournament battles.
        * Plotly bar charts were used to create visualisations of each statistic of highest overall stats. These provided an interactive viewing platform for each visual.
        * Power BI Dashboard, I used a mix of bar charts, line charts and pie charts to summarise the highest overall stats in each characteristic.
    2. **Analyze Type Effectiveness:** Explore how different Pokemon types influence battle outcomes and identify any type advantages.
        * I used plotly bar charts in the Jupyter notebook to understand how the different types would influence the battle.
        * In the Pokemon Dashboard, I used a combination of Bar and Line charts to create the Leading Pokemon scoreboard.
    3. **Player Performance Comparison:** Compare the performance of the two players in the tournament based on their chosen Pokemon and battle results.
        * In the Pokemon Dashboard, in page 2 to 4, I used scatter point, line graphs, bar charts and pie charts to understand the differences in player performances as well as their defense strategies and attacking strategies.
    4. **Visualize Key Stats:** Provide clear visualizations of important attributes such as HP, Attack, Defense, Speed, and their impact on battle outcomes.
        * These attributes can be seen in the page 3 and page 4 of the Pokemon Dashboard with bar charts, line charts and pie charts. They assisted in showing the key attributes in the battle.
    5. **Predict Battle Outcomes:** Use the dataset to build simple predictive models or rules to forecast the winner of a match based on Pokemon stats and types.
        * In the Pokemon Dashboard, on page 5 I created a decomposition tree diagram to do a predictive analysis. This assisted in understanding who was the winner based on the top correlated features.
    6. **User-Friendly Insights:** Present findings in a way that is accessible to both technical and non-technical users, supporting decision-making for future tournaments.
        * The Jupyter notebooks support a technical audience and the Pokemon Dashboard provides information for a non-technical audience. The Dashboard has more design than the notebooks, whereas the notebooks provide more information on why certain plots were produced. For example: the correlation matrix.

## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
    * Power BI did not have any limitations, I did not need to create any geographical map, as there was no location information.
    * Plotly libraries cannot be viewed in GitHub, so they need to be downloaded separately when adding them as screenshots.
* How did you structure the data analysis techniques. Justify your response.
    * I structured my analysis for a technical and non technical audience. The Dashboard design is more fun and has basic visualisations for the tournament, this is for the non-technical audience. The Jupyter notebooks are for the technical audience.
* Did the data limit you, and did you use an alternative approach to meet these challenges? 
    * Yes, there were limitations, as the "pokemon.csv" did not have information about the players and their scores, so I had to add a second dataset called "combats.csv" to provide more information about the tournaments. The way the battles were set between player 1 vs player 2 was random.  
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?
    * I made use of copilot, Chat GPT4.0 to assist me in optimising my code, providing comments and researching Data Ethics and Biases.

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?

    Ethical, Bias, Social & Legal Considerations in a Pokémon Tournament Dataset
    1. Bias & Fairness
    Even synthetic datasets like yours can reinforce or reflect biases when used for prediction or classification.  

        Possible Biases:
        * Game Design Bias: The dataset is shaped by game mechanics — some Pokémon types or stats (e.g., Speed, Attack) are inherently favored.

        * Overrepresentation: Certain types (e.g., Fire, Dragon) may appear more often, skewing models to favor those.

        * Feature Selection Bias: If your model prioritizes only total stats, it may ignore strategic factors like type matchups or held items.

        Why it matters: Training models on biased game outcomes could reinforce unfair advantages and limit diversity in team selection or competitive balancing.

    2. Ethical Use of AI/ML
    While the dataset is from a game, applying models to predict winners, build bots, or automate team selection can raise broader concerns.

        * Automation of Strategy: Reduces human skill in competitive gaming — is it still a fair competition?

        * Unfair Advantage: Players using ML-backed strategies may have a technological edge not accessible to others.

        * AI-generated teams: Could diminish creativity and originality in player decision-making.

        Guideline: Be transparent about when and how machine learning is used in tournaments.

* How did you overcome any legal or societal issues?

    * Social Implications

        Though fictional, how AI models are used in games can shape behavior, competition, and community norms.

        * Exclusion: Models trained on top-tier data might exclude lower-tier Pokémon or players, reinforcing elitism in competitive spaces.
        * Transparency: Predictive tools that are not explained can alienate players.
        * Impact on Learning: Over-reliance on “optimal” predictions may discourage experimentation and exploration by new players.

    * Data Governance

        Even game data should be managed responsibly, especially when shared or used for training models.
        * Data Provenance: Is the battle data from real users? If so, did they consent?
        * Versioning: Are the game mechanics consistent (e.g., Generation VI vs. VIII)? Changes affect model validity.
        * Data Ownership: Pokémon data is IP owned by Nintendo/Game Freak — republishing large portions could violate rights.

    * Legal Considerations

        Pokémon is a trademarked and copyrighted IP, and using its data must comply with its usage policies.
        * Fair Use / Educational Use: If you're using the dataset for academic or hobby projects, it may fall under fair use, but commercial use is risky.
        * Reproducing Artwork, Names, or Lore: Including these in public datasets or models may violate terms of use.
        * Data Sharing: If your dataset includes scraped or user-derived battle logs, be cautious with GDPR or platform-specific policies (e.g., Pokémon Showdown, Smogon).

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.

    * Page 1 - "Scoreboard Overview", 
        "Text box"- used for heading
        "Line and stacked column chart" - "Leading Pokemon Scoreboard of Player 1" 
        "Cards" were used to show the Result, Number of Rounds, Player 1 Total, Player 2 Total, Attch Score: Player 1 and Attack score: Player 2, Defense Score: Player 1, Defense Score: Player 2. Donut Pie charts were used for Player 1 and Player 2 Scores. "Stacked Bar Chart" was used for the highest attacking Score by Player 1.

    * Page 2 - "Player strategy", 
        A "Scatter Chart" was used for the graphic "Higher Attack from Player 1 mostly results in a Win" and "Line Charts" were used for "How players used their Special Defense Power"

    * Page 3 - "Player 1 Statistics", "Stacked Bar chart" was used for the "Fasterst Pokemon group for Player 1" and "Highest Hit for Player 1", a "donut piechart" was used for "Player 1 First Special Attack by Group" and a "Line Chart" for "Highest defense Pokemon for Player 1"

    * Page 4 - "Player 2 Statistics", "Stacked Column Chart" was used for the "Leading Pokemon Scoreboard of Player 2", "Stacked Bar Charts" was used for "Highest Hit for Player 2" and "Attack Power of Player 2" and a "donut pie chart" used for graphic "Player 2 First Special Attack by Group".

    * Page 5 - "Predictive Model", "Decomposition tree" was used to create the Predictive model.

    ![Dashboard page 5](static_images/Dashboard_page5.jpeg)

* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
    * For the non-technical audience, the Pokemon Dashboard was created and for the technical audience the Jupyter notebooks were created.
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 
    * The Dashboard has a more interactive platform that allows the user/ non-technical audience to play around and understand what happens when certain buttons are clicked or graphs are selected.

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
    * Yes, I had to learn how to combine tables in a way that it represents the results of both players. A left join was used twice to perform this action. Also using a tournament dataset is new to me, the structure is different to environmental science datasets.
    * The bug on venv was solved by always selecting the local branch for the python kernal and not the global branch
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.
    * Niel assisted me with my initial bug and I fixed it by selecting the local pathway for the venv file.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
    * How to combine two tables using left joins. I had to read up on how to do it and do research.
    * "venv" file, I asked Emma and Niel for assistence
* What new skills or tools do you plan to learn next based on your project experience? 
    * Train a Machine Learning model using images with CNN

## Deployment
### Power BI

* The Pokemon Dashboard was published under this [link]( https://app.powerbi.com/groups/me/reports/65e2aef0-ec38-434c-adb5-beda3f888e18/72c46320007eaa1686e4?experience=power-bi) called Pokemon Dashboard onto the Power BI workspace website.


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.
    * **pandas**  
        Used for data manipulation and analysis, such as loading CSV files and merging datasets.
        ```python
        import pandas as pd
        pokemon = pd.read_csv('Dataset/raw/pokemon.csv')
        combats = pd.read_csv('Dataset/raw/combats.csv')
        combined = pd.merge(combats, pokemon, left_on='First_pokemon', right_on='#', how='left')
        ```

    * **numpy**  
        Used for numerical operations and handling arrays.
        ```python
        import numpy as np
        stats_mean = np.mean(pokemon['Total'])
        ```

    * **matplotlib**  
        Used for creating static visualizations.
        ```python
        import matplotlib.pyplot as plt
        plt.hist(pokemon['HP'])
        plt.title('Distribution of HP')
        plt.show()
        ```

    * **seaborn**  
        Used for statistical data visualization, such as correlation matrices.
        ```python
        import seaborn as sns
        corr = pokemon.corr()
        sns.heatmap(corr, annot=True)
        plt.show()
        ```

    * **plotly**  
        Used for interactive visualizations.
        ```python
        import plotly.express as px
        fig = px.bar(pokemon, x='Name', y='Total', color='Type 1')
        fig.show()
        ```

    * **scikit-learn**  
        Used for machine learning models and evaluation.
        ```python
        from sklearn.model_selection import train_test_split
        from sklearn.ensemble import RandomForestClassifier

        X = combined[['HP', 'Attack', 'Defense', 'Speed']]
        y = combined['Winner']
        X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
        model = RandomForestClassifier()
        model.fit(X_train, y_train)
        ```

## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

Links:

* https://www.pokemon.com/us/pokedex
* https://pokemondb.net/pokedex
* https://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_National_Pok%C3%A9dex_number





## Acknowledgements (optional)
* I would like to thank my daughter and husband for their support through this project. Also Vasi, Niel and Emma at Code Institute for their support through the Hackethon.
