# Project Instructions
You will apply your data manipulation and analysis skills on the supply chain of ingredients for making an avocado toast in the U.K. You need to determine this information:

- The name of the most common country(s) of origin for three key ingredients: `avocados`, `olive oil`, and `sourdough`.

For the solution, store this most common country of origin for each ingredient as a string, with one string for each country, in the appropriate variable: `top_avocado_origin`, `top_olive_oil_origin`, `top_sourdough_origin`. If there are any hyphens or other letters in the country name data, this needs to be cleaned up so there are only A-Z letters and (maybe) spaces in the name.

**Note:** Because the CSV data files are quite large, and have numerous unused columns, you should subset each of the DataFrames to only include these relevant columns: `'code', 'lc', 'product_name_en', 'quantity', 'serving_size', 'packaging_tags', 'brands', 'brands_tags', 'categories_tags', 'labels_tags', 'countries', 'countries_tags', 'origins','origins_tags'`.

After you complete this project, feel free to analyze this food data for other questions you might be interested in exploring!

## How to approach the project
1. Read in the avocado data
2. Filter avocado data using relevant category tags
3. Where do most UK avocados come from?
4. Create a user-defined function to call for each ingredient
5. Read relevant categories data file and call function for each ingredient


### 1. Read in the avocado data
Begin by reading the avocado data from CSV file in the data folder - it is actually tab-delimited. This creates quite a large DataFrame, so it's a good idea to subset it to only a smaller number of relevant columns. Then read in the file for relevant category tags for avocados.

### 2. Filter avocado data using relevant category tags
Each food DataFrame contains a column called `categories_tags`, which contains the food item category, **e.g., fruits, vegetables, fruit-based oils, etc.** Start by dropping rows with null values in `categories_tags`. This column is comma-separated, so you'll first need to turn it into a column of lists so that you can treat each item in the list as a separate tag. Filter this reduced DataFrame to contain only the rows where there is a relevant category tag.

### 3. Where do most UK avocados come from?
Your avocado DataFrame should contain a column called `origins_tags`. Create a variable called `top_avocado_origin`, containing the top country where avocados in the **United Kingdom** come from.


### 4. Create a user-defined function to call for each ingredient
The golden rule of programming when performing repetitive tasks such as this one is **Don't Repeat Yourself (DRY)**. Turn the code you created to analyze the avocado data and determine its top country of origin into a general function that can be used to do the same with each of the other ingredients. You should also add new steps in it to handle ties, which wasn't necessary for the avocado data.

### 5. Read relevant categories data file and call function for each ingredient
Just as you did with the avocado data, create the variables `top_olive_oil_origin`, and `top_sourdough_origin`, using the relevant category data and analyzing country origin data. To determine these last two origin variables, you'll call the function you've created.