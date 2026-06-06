# swagger

## POZİTİV TESTLƏR

### TC001
* **Title:** POST sorğusu ilə product yaratmaq
* **Description:** POST sorğusu ilə müəyyən ID, ad və price ilə productun yaradılması.
* **Pre-conditions:** Swagger açıqdır və Bearer Token authorization olunub.
* **Steps:**
  1. `POST/products` endpoint-inə klikləyin.
  2. Sağ tərəfdəki **"Try it out"** düyməsinə klikləyin.
  3. Body hissəsinə JSON formatında aşağıdakı məlumatları yazın:
     ```json
     {
       "id": 666,
       "name": "table",
       "price": 60
     }
     ```
  4. **Execute** düyməsinə klikləyin.
* **Expected Results:** Response-da `201 Created` kodu görünür və məhsul uğurla yaradılır.
* **Status:** Passed
* **Priority:** High
* **Severity:** Major
* **Attachment:** ***

---

### TC002
* **Title:** GET sorğusu ilə yaradılmış productu yoxlamaq
* **Description:** GET sorğusu ilə ID daxil edərək yaradılmış product haqqında məlumatın alınması.
* **Pre-conditions:** Swagger açıqdır və Bearer Token authorization olunub.
* **Steps:**
  1. `GET/products/{id}` endpoint-inə klikləyin.
  2. Sağ tərəfdəki **"Try it out"** düyməsinə klikləyin.
  3. Product ID bölməsinə `666` yazın.
  4. **Execute** düyməsinə klikləyin.
* **Expected Results:** Response-da `200 OK` kodu görünür və müəyyən edilmiş məhsulun məlumatları gəlir.
* **Status:** Passed
* **Priority:** High
* **Severity:** Major
* **Attachment:** ***

---

### TC003
* **Title:** PUT sorğusu ile productun qiymətini dəyişmək
* **Description:** PUT sorğusu ilə ID vasitesile ID, price, name daxil edərək müəyyən productun qiymətinin 60-dan 50-e dəyişdirilməsi.
* **Pre-conditions:** Swagger açıqdır və Bearer Token authorization olunub.
* **Steps:**
  1. `PUT/products/{id}` endpoint-inə klikləyin.
  2. Sağ tərəfdəki **"Try it out"** düyməsinə klikləyin.
  3. Product ID bölməsinə `666` yazın.
  4. Body hissəsinə JSON formatında aşağıdakı məlumatları yazın:
     ```json
     {
       "id": 666,
       "name": "table",
       "price": 50
     }
     ```
  5. **Execute** düyməsinə klikləyin.
* **Expected Results:** Response-da `200 OK` kodu görünür və məhsulun qiyməti uğurla dəyişdirilir.
* **Status:** Passed
* **Priority:** High
* **Severity:** Major
* **Attachment:** ***

<br>

## NEQATİV TESTLƏR

### TC004
* **Title:** Mövcud olan 666 ID-li productu yenidən yaratmaq
* **Description:** POST sorğusu ilə hal-hazırda bazada mövcud olan 666 ID-li productun yenidən yaradılması.
* **Pre-conditions:** Swagger açıqdır və Bearer Token authorization olunub.
* **Steps:**
  1. `POST/products` endpoint-inə klikləyin.
  2. Sağ tərəfdəki **"Try it out"** düyməsinə klikləyin.
  3. Body hissəsinə JSON formatında aşağıdakı məlumatları yazın:
     ```json
     {
       "id": 666,
       "name": "TV",
       "price": 3200
     }
     ```
  4. **Execute** düyməsinə klikləyin.
* **Expected Results:** Response-da `409 Conflict` kodu görünür və 666 ID-li məhsulun artıq mövcud olduğu barədə xəta mesajı gəlir.
* **Status:** Passed
* **Priority:** High
* **Severity:** Major
* **Attachment:** ***

---

### TC005
* **Title:** GET sorğusu ilə ID bölməsinə hərf yazmaq
* **Description:** GET sorğusu ilə ID bölməsinə hərf və ya xüsusi simvollar yazaraq product haqqında məlumatın əldə edilməsi.
* **Pre-conditions:** Swagger açıqdır və Bearer Token authorization olunub.
* **Steps:**
  1. `GET/products/{id}` endpoint-inə klikləyin.
  2. Sağ tərəfdəki **"Try it out"** düyməsinə klikləyin.
  3. Product ID bölməsinə `salam!!!` yazın.
  4. **Execute** düyməsinə klikləyin.
* **Expected Results:** Response-da `400 Bad Request` kodu görünür və "id rəqəm olmalıdır" validation yazısı gəlir.
* **Status:** Passed
* **Priority:** High
* **Severity:** Major
* **Attachment:** ***
