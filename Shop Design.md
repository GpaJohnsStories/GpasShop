LAST UPDATE: 2026-01-27 @ 3:42 PM  

Index Page Overview

The GPAS Shop index page serves as a visual storefront, presenting the entire catalog in a warm, shelf‑based layout that feels like browsing a real shop wall. The page combines a left‑to‑right flow of discovery: curated specials on the left, a clean grid of product snapshots in the center, and a dedicated display window on the right that shows full product details when a snapshot is selected.

The design eliminates nested scrolling, keeps navigation simple, and uses framed boxes, wooden shelves, and blackboard elements to maintain the shop’s friendly, handcrafted personality. Visitors can browse quickly through thumbnails, use search and filter tools to narrow results, and view complete product cards without leaving the page. The layout is desktop‑first, with tablet and phone versions planned around the same 305px visual units for consistency across all devices.

All design photos are in github -- gpas-shop repo /photos/
New shop index.html is built and named new-shop-index.html 


🧱 GPAS Shop Index Page — Final Blueprint (Two‑Table Layout, 6‑Wide Grid)
PAGE STRUCTURE

The page contains two side‑by‑side tables:
1. Main Table (left)
    Width ≈ 970px
    Contains:
        Left Special (rows 1–3 and rows 5-7)
        Shop Photo
        Welcome Blackboard
        Search / Filter
        Shelves
        Product thumbnails (6 per row)

2. Display Window Table (right)
    Width = 305px
    Left margin = 0px
    Contains one large framed cell for the full product card
    Behaves like a sticky sidebar
Total page width ≈ 1280px  
(970 main + 5 gap + 305 display)


📐 MAIN TABLE — COLUMN DEFINITIONS

The main table has 11 interior columns plus 2 borders.
Borders
    Left outside border: 10px
    Right outside border: 5px

Interior Columns
    Odd columns (1, 3, 5, 7, 9, 11): 150px content
    Even columns (2, 4, 6, 8, 10): 5px spacers

This gives you 6 content columns separated by 5 thin spacers.
Width Calculation
    6 × 150 = 900px
    5 × 5 = 25px
    Borders = 20px

Total main table width = 945px  
(You can bump spacers to 10px if you want ~970px.)
📏 ROW DEFINITIONS
Rows 1 & 2 — 305px tall

Contain three 305×305px framed boxes:
    Columns 1–3 → Left Special Feature
    (150 + 5 + 150 = 305)
    Columns 4–6 → Shop Photo
    (150 + 5 + 150 = 305)
    Columns 7–9 → Welcome Blackboard
    (150 + 5 + 150 = 305)

Columns 10–11 remain unused in rows 1–2.
Row 3 — 10px

Full‑width wooden shelf
Spans columns 1–11
🔍 Rows 4 & 5 — 305px tall

Search / Filter area:
    Columns 1–3 → Left Special Feature (same as rows 1–2)
    Columns 4–6 → Search Blackboard
    Columns 7–9 → Filter / Sort Blackboard

Columns 10–11 unused.
🪵 Row 6 — 10px

Full‑width wooden shelf
Spans columns 1–11
🧩 PRODUCT GRID (Rows 7–8, 10–11, etc.)

Each product row contains 6 product thumbnails, each 150×150px.
Pattern per row:
    Column 1: Product P1
    Column 2: Spacer
    Column 3: Product P2
    Column 4: Spacer
    Column 5: Product P3
    Column 6: Spacer
    Column 7: Product P4
    Column 8: Spacer
    Column 9: Product P5
    Column 10: Spacer
    Column 11: Product P6

Rows 7 & 8 — 150px tall

Product thumbnails P1–P6
Row 9 — 10px
Wooden shelf

Rows 10 & 11 — 150px tall
Product thumbnails P7–P12

Row 12 — 10px
Wooden shelf

Repeat until all products are shown.


🧭 DISPLAY WINDOW TABLE (RIGHT SIDE)

A completely separate table:
    Width = 305px
    Left outside margin = 0px
    Right outside margin = 10px
    Contains one large cell with a wood frame
    Height = auto (fills page)
    Displays the full product card when a thumbnail is clicked

This table does not scroll with the main table.
📄 FOOTER

A shared footer appears below both tables, containing links to:
    gpaskids.com
    gpasfaith.com
    gpasshop.com

About the /prod/???-???.html Product Card Files

Each product in the shop is stored as a standalone HTML file inside the GitHub repository folder:
Code
/prod/

The filename format is:
Code
XXX-NNN.html

Where:
    XXX = a three‑letter product category code
    NNN = a three‑digit sequential number
    Example: BKS-014.html, FTH-003.html, KID-027.html

These files are not full web pages. They are self‑contained product cards designed to be loaded into the Display Window on the index page.
What Each Product Card Contains

Every product card file includes:
    Product code
    Product title
    Author or version
    Price
    Product URL (for the “Buy” button)
    Image URL
    Description text
    One‑word tags
    Date added
    A 300px‑wide layout designed to fit inside the Display Window frame

The card is already formatted and styled.
The index page does not modify the card — it simply loads it.
How the Index Page Uses These Files
    The index page reads the list of files in /prod/ to determine available products.
    It extracts the product code from the filename to sort and paginate.
    For each product, it loads only the image URL to create the 150×150 thumbnail.
    When a thumbnail is clicked, the full HTML file is loaded into the Display Window table on the right side of the page.
    No rewriting or parsing of the product card is needed — the card is displayed exactly as stored.

Important Notes for GCP
    Do not alter the structure of the product card files.
    Do not embed product cards directly into the index page.
    The index page should only reference these files and load them dynamically.
    The Display Window must be sized to comfortably show the 300px‑wide card.
    The product grid uses only the thumbnail image, not the full card.
    The index page must handle pagination based on the number of product files.
