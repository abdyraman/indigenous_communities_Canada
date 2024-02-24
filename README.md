# indigenous_communities_Canada
This Python script uses web scraping techniques to gather information about indigenous bands in Canada from a specific website. It iterates through band numbers, visits corresponding web pages, extracts band details such as name, number, address, phone, fax, and website, and organizes the data into a pandas DataFrame. The script saves the raw data to an Excel file and then performs data cleaning by removing rows with missing values. The cleaned data is saved to another Excel file, and the web browser used for scraping is closed. The result is two Excel files: one with raw data and another with cleaned data about indigenous bands in Canada.

1. **Importing Dependencies:**
   - `pandas`: Used for data manipulation and analysis.
   - `splinter.Browser`: A tool for browser automation, often used for web scraping.
   - `BeautifulSoup`: A library for pulling data out of HTML and XML files.
   - `selenium.webdriver`: Selenium WebDriver is a web automation framework.
   - `train_test_split`: Function from scikit-learn for splitting datasets into training and testing sets.

2. **Setting Up Splinter:**
   - It initializes a browser object using Chrome for web automation.

3. **Data Collection Loop:**
   - Iterates through band numbers from 1 to 780.
   - Visits a URL for each band number using Splinter.
   - Parses the HTML of the webpage using BeautifulSoup.
   - Extracts information such as band name, number, address, phone, fax, and website.
   - Organizes the extracted data into a dictionary.
   - Appends the dictionary to a list (`all_page_data`).

4. **Creating DataFrame:**
   - Converts the list of dictionaries into a pandas DataFrame (`df`).

5. **Saving Data to Excel:**
   - Saves the initial DataFrame to an Excel file named 'raw_data_indigenous_list.xlsx'.

6. **Cleaning Data:**
   - Drops rows where at least one value is missing (NaN) except if there are fewer than 5 non-NaN values.
   - Resets the index of the DataFrame.

7. **Saving Cleaned Data to Excel:**
   - Saves the cleaned DataFrame to an Excel file named 'cleaned_data_indigenous_list.xlsx'.

8. **Browser Cleanup:**
   - Quits the Splinter browser.

The final result is two Excel files: 'raw_data_indigenous_list.xlsx' containing data from all pages, and 'cleaned_data_indigenous_list.xlsx' with cleaned data excluding rows with insufficient information.
