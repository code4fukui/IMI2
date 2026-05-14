# IMI2 (Government Interoperability Framework - GIF)

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

This repository contains the documentation for Japan's **Government Interoperability Framework (GIF)**, under the project name **IMI2**. GIF is a set of rules, data models, and practical guidebooks designed to enhance data interoperability across government services and with the private sector.

- **Official Policy Page:** [Government Interoperability Framework (GIF)](https://www.digital.go.jp/policies/data_strategy_government_interoperability_framework/)

## Core Concepts

The framework is built on a layered architecture to ensure that data is not only standardized but also practical for implementation. It provides a set of reference models that can be adapted for specific needs while maintaining a common foundation for interoperability.

### Core Data Models
The foundation of GIF is a set of standardized data models for common entities, enabling seamless data exchange and reducing design costs. This integrates existing standards into a unified framework.

- **Purpose**: To standardize fundamental data structures for entities like individuals, corporations, addresses, and facilities.
- **Key Components**:
    - **Core Data Parts**: Uniform formats for common attributes like addresses, dates, and phone numbers to ensure consistent data handling.
    - **Structured Data Types**: Pre-defined structures for complex data like IDs, codes, and roles to maintain consistency.
        - **ID Information Type**: Combines an ID value with its classification (e.g., personal number, employee ID).
        - **Code Information Type**: Links a code to its meaning (e.g., gender code "1" → "Male").
        - **Role Participation Type**: Defines relationships between entities (e.g., a "Guardian" role linked to a person).
- **Primary Documents**:
    - [Core Data Model Overview](430_Core_Data_Model_Overview.md)
    - [Class Diagram](430-1_DMD_Class_Diagram.pdf)
    - [Data Model Description (DMD) Spreadsheet](438_Core_Data_Model_DMD.xlsx)

### Address Management
A standardized approach to handling address data is critical for interoperability. GIF recommends code-based management for accuracy and consistency.

- **Recommended Format (Code-Based)**: Use the **national local public entity code** and **town/area ID** to represent addresses programmatically, preventing variations in text representation.
    - *Example*: `131016` (Chiyoda Ward) + `0002002` (Kasumigaseki) + `1-6` → "東京都千代田区霞が関2-1-6".
- **Textual Format**: A 4-field structure (Prefecture, City/District, Town, Block/Number) is recommended for textual data.
- **English Format**: Follows Hepburn romanization rules.
    - *Example*: `2-1-2 Kasumigaseki, Chiyoda-ku, Tokyo 100-8926, Japan`.
- **Primary Document**: [Core Data Part - Address](442_Core_Data_Part_Address.md)

### Code (Classification System) Implementation
GIF provides guidelines for designing and using codes to ensure data is classified consistently across different systems.

- **Code Types**:
    - **Identification Codes**: Unique identifiers (e.g., My Number, Corporate Number).
    - **Classification Codes**: Categorical codes (e.g., ISO 5218 for gender, Japan Standard Industrial Classification).
- **Design Principles**:
    - **Prefer Existing Standards**: Use ISO and JIS codes where applicable.
    - **Meaningful vs. Meaningless Codes**: Choose between codes that embed semantic information (e.g., `JP-CAS-2017-003`) and flexible, randomized codes (e.g., UUIDs).
    - **Error Prevention**: Use check digits for critical codes to prevent input errors.
- **Primary Document**: [Practical Guidebook for Code Implementation](463-1_Practical_Guidebook_for_Code_(Classification_System)_Implementation.md)

---

## All Documents

### Overview
- [410_GIF_Whole.md](410_GIF_Whole.md)
- [411_GIF_Explanation.pdf](411_GIF_Explanation.pdf) ([pptx](411_GIF_Explanation.pptx))

### Core Vocabulary
- [420_Core_Vocabulary.md](420_Core_Vocabulary.md)

### Core Data Model
- [430_Core_Data_Model_Overview.md](430_Core_Data_Model_Overview.md)
- [430-1_DMD_Class_Diagram.pdf](430-1_DMD_Class_Diagram.pdf)
- [431_Core_Data_Model_Description_Individual.md](431_Core_Data_Model_Description_Individual.md)
- [432_Core_Data_Model_Description_Contact.md](432_Core_Data_Model_Description_Contact.md)
- [433_Core_Data_Model_Description_Address.md](433_Core_Data_Model_Description_Address.md)
- [434_Core_Data_Model_Description_Corporation.md](434_Core_Data_Model_Description_Corporation.md)
- [435_Core_Data_Model_Description_Facility.md](435_Core_Data_Model_Description_Facility.md)
- [436_Core_Data_Model_Description_Accessibility.md](436_Core_Data_Model_Description_Accessibility.md)
- [437_Core_Data_Model_Description_Childcare_Support_Information.md](437_Core_Data_Model_Description_Childcare_Support_Information.md)
- [438_Core_Data_Model_DMD.pdf](438_Core_Data_Model_DMD.pdf) ([xlsx](438_Core_Data_Model_DMD.xlsx))

### Core Data Parts
- [441_Core_Data_Part_Date_Time.md](441_Core_Data_Part_Date_Time.md)
- [442_Core_Data_Part_Address.md](442_Core_Data_Part_Address.md)
- [443_Core_Data_Part_Postal_Code.md](443_Core_Data_Part_Postal_Code.md)
- [444_Core_Data_Part_Geo_Information.md](444_Core_Data_Part_Geo_Information.md)
- [445_Core_Data_Part_Phone_Number.md](445_Core_Data_Part_Phone_Number.md)

### Implementation Data Model - Government
- [451-1_Implementation_Data_Model_Application.md](451-1_Implementation_Data_Model_Application.md)
- [451-1-1_Application_(Individual)_Data_Model