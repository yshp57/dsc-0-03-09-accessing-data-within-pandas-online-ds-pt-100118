
# Accessing Data within Pandas

## Introduction

In this lessomn we're going to dig into various methods for accessing data from our Pandas Series and DaatFrames.

## Objectives
You will be able to:
* Understand and explain some key Pandas methods
* Use simple selectors for series
* Access DataFrame data by using the label
* Perform boolean indexing on both Series and DataFrames
* Set new Series and DataFrame inputs

# Import Package


```python
import pandas as pd
```

# The .head() method()

Here we load the dataset, print the lenght (the number of rows), and preview the first 5 rows.


```python
df = pd.read_csv('WorldCupMatches.csv')
print(len(df))
df.head()
```

    4572





<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4.0</td>
      <td>1.0</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201.0</td>
      <td>1096.0</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 4</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>USA</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>Belgium</td>
      <td></td>
      <td>18346.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>MACIAS Jose (ARG)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201.0</td>
      <td>1090.0</td>
      <td>USA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1930.0</td>
      <td>14 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>Brazil</td>
      <td></td>
      <td>24059.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>TEJADA Anibal (URU)</td>
      <td>VALLARINO Ricardo (URU)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>201.0</td>
      <td>1093.0</td>
      <td>YUG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1930.0</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3.0</td>
      <td>1.0</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201.0</td>
      <td>1098.0</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930.0</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201.0</td>
      <td>1085.0</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
  </tbody>
</table>
</div>



# We can also preview the last (n) rows


```python
df.tail(2)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4570</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4571</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



# .shape()
You can also get both the number of rows and columns with the .shape attribute (notice no parentheses!)


```python
df.shape
```




    (4572, 20)



# Getting Column Names


```python
df.columns
```




    Index(['Year', 'Datetime', 'Stage', 'Stadium', 'City', 'Home Team Name',
           'Home Team Goals', 'Away Team Goals', 'Away Team Name',
           'Win conditions', 'Attendance', 'Half-time Home Goals',
           'Half-time Away Goals', 'Referee', 'Assistant 1', 'Assistant 2',
           'RoundID', 'MatchID', 'Home Team Initials', 'Away Team Initials'],
          dtype='object')



# Getting Data types


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 4572 entries, 0 to 4571
    Data columns (total 20 columns):
    Year                    852 non-null float64
    Datetime                852 non-null object
    Stage                   852 non-null object
    Stadium                 852 non-null object
    City                    852 non-null object
    Home Team Name          852 non-null object
    Home Team Goals         852 non-null float64
    Away Team Goals         852 non-null float64
    Away Team Name          852 non-null object
    Win conditions          852 non-null object
    Attendance              850 non-null float64
    Half-time Home Goals    852 non-null float64
    Half-time Away Goals    852 non-null float64
    Referee                 852 non-null object
    Assistant 1             852 non-null object
    Assistant 2             852 non-null object
    RoundID                 852 non-null float64
    MatchID                 852 non-null float64
    Home Team Initials      852 non-null object
    Away Team Initials      852 non-null object
    dtypes: float64(8), object(12)
    memory usage: 714.5+ KB


# Series / Columns


```python
df['Year'].head(3) #You can use the .head() method on a series as well as a dataframe
```




    0    1930.0
    1    1930.0
    2    1930.0
    Name: Year, dtype: float64



equivalently,


```python
df.Year.head(3)
```




    0    1930.0
    1    1930.0
    2    1930.0
    Name: Year, dtype: float64



### Datatypes for Columns


```python
df.Year.dtype
```




    dtype('float64')



# .iloc()
You can also access specific rows of a dataframe or specific items in a series using the .iloc() method.


```python
df.iloc[0]
```




    Year                                      1930
    Datetime                  13 Jul 1930 - 15:00 
    Stage                                  Group 1
    Stadium                                Pocitos
    City                               Montevideo 
    Home Team Name                          France
    Home Team Goals                              4
    Away Team Goals                              1
    Away Team Name                          Mexico
    Win conditions                                
    Attendance                                4444
    Half-time Home Goals                         3
    Half-time Away Goals                         0
    Referee                 LOMBARDI Domingo (URU)
    Assistant 1              CRISTOPHE Henry (BEL)
    Assistant 2                REGO Gilberto (BRA)
    RoundID                                    201
    MatchID                                   1096
    Home Team Initials                         FRA
    Away Team Initials                         MEX
    Name: 0, dtype: object




```python
# Notice how this is the top row
df.head(1)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4.0</td>
      <td>1.0</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201.0</td>
      <td>1096.0</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
  </tbody>
</table>
</div>



# Notice how you can chain either way


```python
df.Year.iloc[0] #The Year Series at index 0
```




    1930.0




```python
df.iloc[0]['Year'] #Row 0 of the DataFrame, entry for 'Year' field
```




    1930.0



# Subsetting with Conditionals

Notice we can check a condition against a series like this:


```python
df['Home Team Name'] == 'France'
```




    0        True
    1       False
    2       False
    3       False
    4       False
    5       False
    6       False
    7       False
    8       False
    9       False
    10      False
    11      False
    12      False
    13      False
    14      False
    15      False
    16      False
    17      False
    18      False
    19      False
    20      False
    21      False
    22      False
    23      False
    24      False
    25      False
    26      False
    27      False
    28      False
    29      False
            ...  
    4542    False
    4543    False
    4544    False
    4545    False
    4546    False
    4547    False
    4548    False
    4549    False
    4550    False
    4551    False
    4552    False
    4553    False
    4554    False
    4555    False
    4556    False
    4557    False
    4558    False
    4559    False
    4560    False
    4561    False
    4562    False
    4563    False
    4564    False
    4565    False
    4566    False
    4567    False
    4568    False
    4569    False
    4570    False
    4571    False
    Name: Home Team Name, Length: 4572, dtype: bool



We can pass this similar to how we call a column in general to filter the dataframe to those rows that meet or criteria.


```python
france_home = df[df['Home Team Name']=='France']
print(len(france_home))
france_home.head()
```

    31





<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4.0</td>
      <td>1.0</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201.0</td>
      <td>1096.0</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>37</th>
      <td>1938.0</td>
      <td>05 Jun 1938 - 17:00</td>
      <td>First round</td>
      <td>Stade Olympique</td>
      <td>Colombes</td>
      <td>France</td>
      <td>3.0</td>
      <td>1.0</td>
      <td>Belgium</td>
      <td></td>
      <td>30454.0</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>WUETHRICH Hans (SUI)</td>
      <td>KRIST Gustav (TCH)</td>
      <td>BIRLEM Alfred (GER)</td>
      <td>206.0</td>
      <td>1146.0</td>
      <td>FRA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>85</th>
      <td>1954.0</td>
      <td>19 Jun 1954 - 17:10</td>
      <td>Group 1</td>
      <td>Charmilles</td>
      <td>Geneva</td>
      <td>France</td>
      <td>3.0</td>
      <td>2.0</td>
      <td>Mexico</td>
      <td></td>
      <td>19000.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>ASENSI Manuel (ESP)</td>
      <td>FRANKEN Laurent (BEL)</td>
      <td>BAUMBERGER Rene (SUI)</td>
      <td>211.0</td>
      <td>1275.0</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>105</th>
      <td>1958.0</td>
      <td>08 Jun 1958 - 19:00</td>
      <td>Group 2</td>
      <td>Idrottsparken</td>
      <td>Norrk�Ping</td>
      <td>France</td>
      <td>7.0</td>
      <td>3.0</td>
      <td>Paraguay</td>
      <td></td>
      <td>16518.0</td>
      <td>2.0</td>
      <td>2.0</td>
      <td>GARDEAZABAL Juan (ESP)</td>
      <td>GRIFFITHS Benjamin (WAL)</td>
      <td>BROZZI Juan (ARG)</td>
      <td>220.0</td>
      <td>1386.0</td>
      <td>FRA</td>
      <td>PAR</td>
    </tr>
    <tr>
      <th>122</th>
      <td>1958.0</td>
      <td>15 Jun 1958 - 19:00</td>
      <td>Group 2</td>
      <td>Eyravallen</td>
      <td>Orebro</td>
      <td>France</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>Scotland</td>
      <td></td>
      <td>13554.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>BROZZI Juan (ARG)</td>
      <td>ORLANDINI Vincenzo (ITA)</td>
      <td>WYSSLING Paul (SUI)</td>
      <td>220.0</td>
      <td>1387.0</td>
      <td>FRA</td>
      <td>SCO</td>
    </tr>
  </tbody>
</table>
</div>



We can also use the '~' to negate clauses:


```python
not_france_home = df[~(df['Home Team Name']=='France')] #Notice we also need parentheses
print(len(not_france_home))
not_france_home.head()
```

    4541





<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 4</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>USA</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>Belgium</td>
      <td></td>
      <td>18346.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>MACIAS Jose (ARG)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201.0</td>
      <td>1090.0</td>
      <td>USA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1930.0</td>
      <td>14 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>Brazil</td>
      <td></td>
      <td>24059.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>TEJADA Anibal (URU)</td>
      <td>VALLARINO Ricardo (URU)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>201.0</td>
      <td>1093.0</td>
      <td>YUG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1930.0</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3.0</td>
      <td>1.0</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201.0</td>
      <td>1098.0</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930.0</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201.0</td>
      <td>1085.0</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1930.0</td>
      <td>16 Jul 1930 - 14:45</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Chile</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>Mexico</td>
      <td></td>
      <td>9249.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>APHESTEGUY Martin (URU)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>201.0</td>
      <td>1095.0</td>
      <td>CHI</td>
      <td>MEX</td>
    </tr>
  </tbody>
</table>
</div>



# The .isnull() method

Filtering null values is a common practice so the .isnull() method is an easy way to determine whether or not an entry is populated.


```python
no_year = df[df.Year.isnull()]
print(len(no_year))
no_year.head()
```

    3720





<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>852</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>853</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>854</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>855</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>856</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



More commonly, we might want to return all of the rows that are not null:


```python
df[~df.Year.isnull()].head() #The tilde (~) negates the boolean, making every True statement False and vice versa.
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Datetime</th>
      <th>Stage</th>
      <th>Stadium</th>
      <th>City</th>
      <th>Home Team Name</th>
      <th>Home Team Goals</th>
      <th>Away Team Goals</th>
      <th>Away Team Name</th>
      <th>Win conditions</th>
      <th>Attendance</th>
      <th>Half-time Home Goals</th>
      <th>Half-time Away Goals</th>
      <th>Referee</th>
      <th>Assistant 1</th>
      <th>Assistant 2</th>
      <th>RoundID</th>
      <th>MatchID</th>
      <th>Home Team Initials</th>
      <th>Away Team Initials</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 1</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>France</td>
      <td>4.0</td>
      <td>1.0</td>
      <td>Mexico</td>
      <td></td>
      <td>4444.0</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>LOMBARDI Domingo (URU)</td>
      <td>CRISTOPHE Henry (BEL)</td>
      <td>REGO Gilberto (BRA)</td>
      <td>201.0</td>
      <td>1096.0</td>
      <td>FRA</td>
      <td>MEX</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1930.0</td>
      <td>13 Jul 1930 - 15:00</td>
      <td>Group 4</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>USA</td>
      <td>3.0</td>
      <td>0.0</td>
      <td>Belgium</td>
      <td></td>
      <td>18346.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>MACIAS Jose (ARG)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>201.0</td>
      <td>1090.0</td>
      <td>USA</td>
      <td>BEL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1930.0</td>
      <td>14 Jul 1930 - 12:45</td>
      <td>Group 2</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Yugoslavia</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>Brazil</td>
      <td></td>
      <td>24059.0</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>TEJADA Anibal (URU)</td>
      <td>VALLARINO Ricardo (URU)</td>
      <td>BALWAY Thomas (FRA)</td>
      <td>201.0</td>
      <td>1093.0</td>
      <td>YUG</td>
      <td>BRA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1930.0</td>
      <td>14 Jul 1930 - 14:50</td>
      <td>Group 3</td>
      <td>Pocitos</td>
      <td>Montevideo</td>
      <td>Romania</td>
      <td>3.0</td>
      <td>1.0</td>
      <td>Peru</td>
      <td></td>
      <td>2549.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>WARNKEN Alberto (CHI)</td>
      <td>LANGENUS Jean (BEL)</td>
      <td>MATEUCCI Francisco (URU)</td>
      <td>201.0</td>
      <td>1098.0</td>
      <td>ROU</td>
      <td>PER</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1930.0</td>
      <td>15 Jul 1930 - 16:00</td>
      <td>Group 1</td>
      <td>Parque Central</td>
      <td>Montevideo</td>
      <td>Argentina</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>France</td>
      <td></td>
      <td>23409.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>REGO Gilberto (BRA)</td>
      <td>SAUCEDO Ulises (BOL)</td>
      <td>RADULESCU Constantin (ROU)</td>
      <td>201.0</td>
      <td>1085.0</td>
      <td>ARG</td>
      <td>FRA</td>
    </tr>
  </tbody>
</table>
</div>



# The .str.contains() method

Or we can use string methods to filter based on text:


```python
df[df['Home Team Name'].str.contains('M')]
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-26-0ac63b914d2a> in <module>()
    ----> 1 df[df['Home Team Name'].str.contains('M')]
    

    ~\Anaconda3wenv\lib\site-packages\pandas\core\frame.py in __getitem__(self, key)
       1956         if isinstance(key, (Series, np.ndarray, Index, list)):
       1957             # either boolean or fancy integer index
    -> 1958             return self._getitem_array(key)
       1959         elif isinstance(key, DataFrame):
       1960             return self._getitem_frame(key)


    ~\Anaconda3wenv\lib\site-packages\pandas\core\frame.py in _getitem_array(self, key)
       1983     def _getitem_array(self, key):
       1984         # also raises Exception if object array with NA values
    -> 1985         if com.is_bool_indexer(key):
       1986             # warning here just in case -- previously __setitem__ was
       1987             # reindexing but __getitem__ was not; it seems more reasonable to


    ~\Anaconda3wenv\lib\site-packages\pandas\core\common.py in is_bool_indexer(key)
        187             if not lib.is_bool_array(key):
        188                 if isnull(key).any():
    --> 189                     raise ValueError('cannot index with vector containing '
        190                                      'NA / NaN values')
        191                 return False


    ValueError: cannot index with vector containing NA / NaN values


## Summary

We've introduded a range of techniques for accessing data from Pandas Series and DataFrames. As you see above, though, this is one of many reasons why we might need to remove (or fill) null values. Which leads us to some time for practice! Lets on to the lab where you will get a chance to combine some of these methods!
