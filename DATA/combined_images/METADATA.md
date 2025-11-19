# **ASL Image Dataset**

---

## **Data Summary**

This dataset was retrieved from Mendeley Data and contains 5,200 labeled PNG images representing hand-shaped signs of the American Sign Language (ASL) alphabet. The dataset includes all static letters except **J** and **Z**, which require motion and cannot be captured in a still image. It also includes two additional signs: **SP** (Space) and **FN** (Finish).

All images are clearly labeled with their corresponding letter or symbol.

**Dataset in Repository:**
[https://github.com/arotwell/DS-4002-Project3.git](https://github.com/arotwell/DS-4002-Project3.git)

---

## **Provenance**

* **Source:** [https://data.mendeley.com/datasets/xs6mvhx6rh/1](https://data.mendeley.com/datasets/xs6mvhx6rh/1)
* **Imported To:** [https://github.com/arotwell/DS-4002-Project3.git](https://github.com/arotwell/DS-4002-Project3.git)
* **Dataset Name:** ASL Alphabet Image Dataset
* **Collection Method:** Images were downloaded directly from the Mendeley archive and used as input for our CNN and ResNet classification models.

---

## **LICENSE**

### **1. Project Code License — MIT License**

Copyright (c) 2025
Andrew Otwell, Zoe Gates, Katrina Garcia

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit others to do so—subject to the following conditions:

The copyright notice and permission notice must be included in all copies or
substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS,” WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED.

---

### **2. Data Source License — CC BY 4.0**

The ASL image dataset is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

This license allows sharing and adaptation as long as proper attribution is provided, a link to the license is included, and any changes are indicated. Some elements may require additional permission if attributed to a third party.

License Details: [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)

---

## **Ethical Considerations**

This project focuses on classifying ASL hand-sign images for academic and educational purposes only.

### **Key Ethical Notes**

* **Public Data Only:** All images come from a publicly available, openly licensed dataset.
* **No Personal Identifiers:** Images contain only hands; no identifying features are included.
* **Respect for ASL Community:** This work does not replace ASL instruction or interpretation.
* **Academic Use Only:** Results and models are intended for coursework, not deployment or commercial use.

---

## **Data Dictionary**

| Field Name | Data Type | Description                                  | Allowed Values / Range            | Example         |
| ---------- | --------- | -------------------------------------------- | --------------------------------- | --------------- |
| **Image**  | PNG       | Image file containing a single ASL hand sign | PNG file                          | `User4_X_1.png` |
| **Label**  | String    | Corresponding ASL character label            | A–Z (excluding J, Z), plus SP, FN | `a`             |

---

## **Exploratory Data Analysis**

<img width="400" height="400" src="https://github.com/arotwell/DS-4002-Project3/blob/e34e1a8da3475cf34712edca8b60544825f79c7e/OUTPUT/q1.png?raw=true" />
<img width="400" height="400" src="https://github.com/arotwell/DS-4002-Project3/blob/e34e1a8da3475cf34712edca8b60544825f79c7e/OUTPUT/q2.png?raw=true" />


