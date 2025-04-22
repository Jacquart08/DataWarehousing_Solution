# Data-Warehousing Project
________________________________________________________________________________________

**A24 / DSTI - School of Engineering**
________________________________________________________________________________________

## What is the purpose of this project
For this project, we selected a comprehensive Kaggle dataset focusing on the PlayStation ecosystem, containing real-world data spanning from 2008 to 2024. This dataset consists of six CSV files, all of which were integrated into our ETL pipeline to enable detailed analyses of the gaming market, players behaviors, and sales dynamics. 
Notably, the dataset provides detailed information on in-game achievements earned by players, offering valuable insights into user engagement and gaming patterns. Given the substantial size of the dataset with each table containing millions of rows, it serves as an excellent foundation for practicing advanced data warehousing techniques and conducting extensive in-depth analyses.

## Data dictionnary of the dataset
To facilitate the understanding of the dataset, we provide below a comprehensive data dictionary outlining the structure, meaning and relationships between the various tables and fields represented:
| 🧩 Table        | 🏷️ Colonne         | 🧬 Type de Donnée   | 🔑 Type de Clé     |
|----------------|--------------------|---------------------|--------------------|
| 🎮 **GAMES**   | GameID             | `VARCHAR(50)`       | **PK**             |
|                | Title              | `VARCHAR(255)`      |                    |
|                | Platform           | `VARCHAR(50)`       |                    |
|                | Developper         | `VARCHAR(50)`       |                    |
|                | Publishers         | `VARCHAR(50)`       |                    |
|                | Genres             | `VARCHAR(255)`      |                    |
|                | Supported          | `BOOLEAN`           |                    |
|                | Released_Dates     | `DATETIME`          |                    |
 
---
 
| 🧑‍💻 **PLAYERS** | PlayerID           | `VARCHAR(20)`       | **PK**             |
|                 | Nickname           | `VARCHAR(50)`       |                    |
|                 | Country            | `VARCHAR(60)`       |                    |
 
---
 
| 🛒 **PURCHASED_GAMES** | PlayerID     | `VARCHAR(50)`       | **FK**             |
|                        | Library      | `VARCHAR(255)`      |                    |
 
---
 
| 💰 **PRICE**    | GameID             | `VARCHAR(50)`       | **FK**             |
|                 | Eur                | `DT_NUM(18,2)`      |                    |
|                 | Date_Acquired      | `DATETIME`          |                    |
 
---
 
| 🏆 **ACHIEVEMENTS** | AchievementID  | `VARCHAR(50)`       | **Composite PK**   |
|                     | GameID         | `VARCHAR(10)`       | **FK**             |
|                     | Title          | `VARCHAR(255)`      |                    |
|                     | Description    | `VARCHAR(255)`      |                    |
|                     | Rarity         | `VARCHAR(20)`       |                    |
 
---
 
| 📜 **HISTORY**  | PlayerID           | `VARCHAR(10)`       | **FK**             |
|                 | AchievementID      | `VARCHAR(20)`       |                    |


## Instruction
1. Database Initialization

Before opening the SSIS solution, please execute all the SQL queries contained in the following file:

    - create_DB_and_Tables.sql


2. Configure the CSV File Path

Once the .sln solution is open in Visual Studio, go to Solution Explorer, double-click on Project.params, and change the value by specifying your absolute path to the folder that contains the CSV files. Make sure the path ends with a backslash (\).

Exemple : C:\User\YourPath\
