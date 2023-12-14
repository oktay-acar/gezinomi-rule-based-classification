# Calculating Lead-Based Returns with Rule-Based Classification using [Gezinomi](https://www.gezinomi.com/)'s Dataset

**Business Problem**

**Gezinomi** wants to create new level-based sales definitions by using some of the features of the sales it makes, and to create segments according to these new sales definitions and to estimate how much the new customers can earn on average according to these segments.

For Example: It is desired to determine how much a customer who wants to go to an All Inclusive hotel from Antalya during a busy period can earn on average. 

**Dataset Story**

**gezinomi.xlsx** dataset contains the prices of the sales made by **Gezinomi** company and information about these sales. The dataset consists of records created in each sales transaction. This means that the table is not deduplicated. In other words, the customer may have made more than one purchase.

**Variables**
- **SaleId:** Sales id
- **SaleDate:** Sale Date
- **CheckInDate:** Customer's check-in date
- **Price:** Price paid for sale
- **ConceptName:** Hotel concept information
- **SaleCityName:** The city where the hotel is located
- **CInDay:** Customer's check-in day
- **SaleCheckInDayDiff:** Check in and check in date difference
- **Season:** Season information on the check-in date

**Before Application:**
| &nbsp; | SaleId | SaleDate  | CheckInDate |  Price   |  ConceptName   | SaleCityName |  CInDay  | SaleCheckInDayDiff | Seasons |
| :----: | :----: | :-------: | :---------: | :------: | :------------: | :----------: | :------: | :----------------: | :-----: |
|   0    | 415122 | 12/3/2022 |  12/3/2022  | 79.30403 |  Herşey Dahil  |   Antalya    | Saturday |         0          |   Low   |
|   1    | 415103 | 12/3/2022 |  12/3/2022  | 45.9707  | Yarım Pansiyon |   Antalya    | Saturday |         0          |   Low   |
|   2    | 404034 | 9/12/2022 |  9/13/2022  | 77.83883 |  Herşey Dahil  |   Antalya    | Tuesday  |         1          |  High   |
|   3    | 415094 | 12/3/2022 | 12/10/2022  | 222.7106 | Yarım Pansiyon |    İzmir     | Saturday |         7          |   Low   |
|   4    | 414951 | 12/1/2022 |  12/3/2022  | 140.4762 | Yarım Pansiyon |    İzmir     | Saturday |         2          |   Low   |

**Expected Output:**
| &nbsp; |     sales_level_based     |  Price   | SEGMENT |
| :----: | :-----------------------: | :------: | :-----: |
|   0    |  GIRNE_HERŞEY DAHIL_HIGH  | 103.9354 |    A    |
|   1    |  GIRNE_HERŞEY DAHIL_LOW   | 90.93594 |    A    |
|   2    | İZMIR_YARIM PANSIYON_HIGH | 87.6573  |    A    |
|   3    |  DIĞER_HERŞEY DAHIL_LOW   | 87.31088 |    A    |
|   4    |  DIĞER_HERŞEY DAHIL_HIGH  | 83.78727 |    A    |

---

## Requirements
~~~python
pandas==1.5.1
~~~

---

## Author
[Oktay Acar](https://github.com/oktay-acar)