### README: Electric Vehicle (EV) Sales Data Scraper

---

## **Overview**

This script is a web scraper designed to extract and save electric vehicle (EV) sales data from a specified website. The tool supports retrieving data across multiple months and saves the results in a structured CSV file.

### **Key Features**
1. Automatically navigates the website using a Selenium-powered headless browser.
2. Extracts sales data, including vehicle model, sales numbers, manufacturer, price, and additional parameters.
3. Handles multiple pages of data for specified months.
4. Includes robust error handling and logging for debugging.
5. Saves extracted data as a CSV file for further analysis.

---

## **Environment Setup**

### **Prerequisites**
Ensure the following software and libraries are installed before running the script:
1. **Python** (Version 3.7 or later)
2. **Chrome Browser**
3. **Google ChromeDriver** (managed automatically by `webdriver-manager`)

### **Required Python Libraries**
Install the necessary Python packages using pip:
```bash
pip install numpy pandas beautifulsoup4 selenium webdriver-manager tqdm lxml
```

---

## **How to Run**

### **1. Prepare the Environment**
- Ensure Chrome is installed on your machine.
- Confirm Python and required libraries are set up correctly.

### **2. Execute the Script**
Run the script using the following command:
```bash
python scraper.py
```

### **3. Default Behavior**
- The script fetches EV sales data from January 2014 to December 2023.
- Data is saved as a CSV file named `ev_sales_<month>.csv` in the current directory.

### **4. Customizing the Month**
To specify the latest month for data collection, modify the `month` parameter in the function call:
```python
get_ev_data(month="202312")
```
This example fetches data up to December 2023.

---

## **Key Functionalities**

### **Setup Driver**
- The script initializes a headless Chrome browser using Selenium to scrape data.

### **Error Handling**
- Implements retries for failed web page loads (`max_retries=3`).
- Logs errors and program execution details to a log file.

### **Data Extraction**
- Extracts table data from HTML using BeautifulSoup.
- Automatically handles pagination and retrieves all pages for a given month.

### **Output**
- Outputs a structured CSV file containing the following columns:
  - **序号**: Serial Number
  - **车型**: Vehicle Model
  - **销量**: Sales
  - **厂商**: Manufacturer
  - **价格**: Price
  - **参数链接**: Parameter Link
  - **月份**: Month

---

## **Key Considerations**

1. **Website Accessibility**
   - Ensure the target website is accessible during scraping. If the structure changes, update the selectors in the code.

2. **Timeouts**
   - Adjust timeout values in `WebDriverWait` if experiencing delays during loading.

3. **Log Files**
   - Execution logs are saved as `ev_scraper_<timestamp>.log` for troubleshooting.

4. **Large Data Volume**
   - For extended date ranges, the script may take significant time to execute. Use smaller ranges if needed.

5. **Browser Compatibility**
   - The script uses Chrome. Ensure `webdriver-manager` can automatically download a compatible version of ChromeDriver.

---

## **Example Output**

### **Sample CSV File Structure**
| 序号 | 车型     | 销量 | 厂商     | 价格   | 参数链接 | 月份     |
|------|----------|------|----------|--------|----------|----------|
| 1    | Model X  | 500  | Tesla    | $80,000| URL      | 202212   |
| 2    | Model Y  | 700  | Tesla    | $60,000| URL      | 202212   |

---

## **Troubleshooting**

- **Common Issues**
  - *Driver Initialization Fails*: Check Chrome installation and compatibility with ChromeDriver.
  - *No Data Collected*: Verify website structure and update selectors as needed.
  - *Timeouts*: Increase `WebDriverWait` duration for slower page loads.

- **Contact for Support**
  If further issues arise, review the log file for detailed error messages.

---

### **Enjoy using the EV Sales Data Scraper!**
