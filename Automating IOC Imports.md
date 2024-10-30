# 🌟 Automating IOC Imports in Microsoft Defender XDR

There’s an option to upload a full IOC file, rather than adding each IOC manually, one by one. To do this, Microsoft provides a template where you can input all IOCs, allowing for batch uploading. In this guide, I'll show you how to use this method and introduce a solution for automatic detection of IOC types, so you don't have to enter them manually.

**⚠️ Note:** Microsoft’s system can avoid duplicates, so there’s no need to worry about errors or issues caused by duplicates.

![image](https://github.com/user-attachments/assets/473635f3-92a2-4120-93a2-c4d6c5679685)

---

## Steps to Import IOCs in Microsoft Defender XDR

### 1. Navigate to Import Settings
- In the **Microsoft Defender XDR** platform, go to:  
  **System** > **Settings** > **Endpoints** > **Indicators**.

### 2. Download the IOC Template
- Click on the **Import** button.
- Download Microsoft’s template by clicking the **"download sample CSV"** button.

### 3. Prepare the Template
- Delete the sample data in the Excel file provided by Microsoft (it’s just an example).
- Add all IOCs under the **IndicatorValue** column.
- Enter additional information you want to include for each IOC in the remaining columns.

### 4. Automate IOC Type Detection
- In the **IndicatorType** column, instead of manually entering each IOC type, insert the following formula in the top field:

    ```excel
    =IF(AND(ISNUMBER(FIND(".", B2)), NOT(ISNUMBER(FIND("/", B2)))), "DomainName", 
    IF(AND(ISNUMBER(FIND(".", B2)), ISNUMBER(FIND("/", B2))), "Url", 
    IF(COUNTIF(B2, "*.*.*.*")=1, "IpAddress", 
    IF(LEN(B2)=40, "FileSha1", 
    IF(LEN(B2)=64, "FileSha256", "Unknown")))))
    ```

- Hold down the **Ctrl** key and drag the column down to the last IOC in the list. This action should automatically assign the appropriate type based on each IOC.

### 5. Verify the Results
- The result should display each IOC with its correct type.

![image](https://github.com/user-attachments/assets/90d9a87d-0c58-4a06-b26d-0f304fc72fc2)

---

## Uploading the Document

1. In **Microsoft Defender XDR**, navigate to:  
   **System** > **Settings** > **Endpoints** > **Indicators**.
   
2. Click on the **Import** button again, upload the document by clicking **choose file**, then click the **Import** button at the bottom of the screen.

---

## Verifying the Upload

To ensure the IOCs uploaded correctly, use the search field to locate and verify the newly imported IOCs.
