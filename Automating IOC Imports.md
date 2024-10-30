# Automating IOC Imports in Microsoft Defender XDR

---

### Overview
In Microsoft Defender XDR, you can upload a complete IOC (Indicator of Compromise) file, avoiding the need to add each IOC entry individually. Microsoft provides a template that lets you list all IOCs for a streamlined import process. This guide will walk you through the steps for using this template, and show you how to automate IOC type detection without manually specifying the type.

> **Note**: Microsoft’s system automatically handles duplicates, so there's no need to worry about errors or delays due to duplicate entries.

---

### Steps to Import IOCs in Microsoft Defender XDR

1. ### **Access the Import Feature**  
   In Microsoft Defender XDR, navigate to:
   - **System > Settings > Endpoints > Indicators**
   - Click on the **Import** button.

2. ### **Download the Template**  
   - Select **Download sample CSV** to obtain Microsoft’s IOC template.

3. ### **Prepare the Template**  
   - Open the downloaded template in Excel.
   - Delete any example data in the template.
   - In the **IndicatorValue** column, add your IOCs (e.g., domains, URLs, IP addresses, file hashes).

4. ### **Automate IOC Type Detection**  
   - In the **IndicatorType** column, enter the following formula to automatically detect each IOC type:
     ```excel
     =IF(AND(ISNUMBER(FIND(".", B2)), NOT(ISNUMBER(FIND("/", B2)))), "DomainName", IF(AND(ISNUMBER(FIND(".", B2)), ISNUMBER(FIND("/", B2))), "Url", IF(COUNTIF(B2, "*.*.*.*")=1, "IpAddress", IF(LEN(B2)=40, "FileSha1", IF(LEN(B2)=64, "FileSha256", "Unknown")))))
     ```
   - Hold **Ctrl** and drag this formula down to apply it to all entries in the IndicatorType column. This formula will assign each IOC the correct type based on its format.

5. ### **Upload the Document**  
   - Return to **System > Settings > Endpoints > Indicators** in Microsoft Defender XDR.
   - Click **Import** again, then **Choose File** to select your prepared document.
   - Finally, click **Import** at the bottom of the screen.

6. ### **Verify the Upload**  
   - After the upload, use the search field to verify that all IOCs were successfully imported.

---

### Summary
By following these steps, you can simplify the import and categorization process for IOCs in Microsoft Defender XDR. This approach allows for automation in identifying IOC types without manual input, enhancing your workflow efficiency.

---  
