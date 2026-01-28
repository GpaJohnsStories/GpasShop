LAST UPDATE: 2026-01-28 @ 4:32 PM

Index Page Overview

The GPAS Shop index page serves as a visual storefront, presenting the entire catalog in a warm, shelf‑based layout that feels like browsing a real shop wall. The page combines a left‑to‑right flow of discovery: curated specials on the left, a clean grid of product snapshots in the center, and a dedicated display window on the right that shows full product details when a snapshot is selected.

The design eliminates nested scrolling, keeps navigation simple, and uses framed boxes, wooden shelves, and blackboard elements to maintain the shop’s friendly, handcrafted personality. Visitors can browse quickly through thumbnails, use search and filter tools to narrow results, and view complete product cards without leaving the page. The layout is desktop‑first, with tablet and phone versions planned around the same 305px visual units for consistency across all devices.

*** STYLE NOTES ***
    All design photos are in github -- gpas-shop repo /photos/
    New shop index.html is built and named new-shop-index.html 

🧱 GPAS Shop Index Page — Final Blueprint (3‑Table Layout

🧱 TABLE 1 — WELCOME TABLE (Top‑Left)
    Width: 908px (300 + 4 + 300 + 4 + 300)
    Height: 300px
    Left outside buffer: 10px
    Right outside buffer: 8px
        Below Table 1: 8px vertical buffer before Table 3 begins

Row 1 (300px tall)
    Col 1 — 300px
        Special Product 1
        Background image: wood-background.png (blackboard frame)
        Image can scale to fit the 300×300 cell
    Col 2 — 4px
        Divider
        Transparent (shows linen-background.jpg through it)
    Col 3 — 300px
        Shop Photo
        Background image: gpas-shop-web.png
        Scales to fit the 300×300 cell
    Col 4 — 4px
        Divider
        Transparent
    Col 5 — 300px
        Welcome text -- kalam 24px, ???, bold ???, chaulk white on blackboard
        Background image: wood-background.png
        Text sits on top of the blackboard image

Row 2 — 4px tall (rowspan background row)
        This row is a spacer row that visually separates the top blackboards from the second row of blackboards.
        Height: 4px
        All 5 columns exist, but:
            No borders
            No images
            No lines
            Transparent background
                Purpose: allow the linen page background to show through as a clean gap
            No content, no padding
            This row is intentionally “empty” so the page background creates a natural breathing space.

Row 3 — 150px tall (second blackboard row)
Same 5‑column structure as Row 1, but every cell is a blackboard.
    Col 1 (300px): Blackboard (wood frame)
    Col 2 (4px): Divider (transparent)
    Col 3 (300px): Blackboard (wood frame)
    Col 4 (4px): Divider (transparent)
    Col 5 (300px): Blackboard (wood frame)
    Notes:
        These blackboards can hold:
            Search instructions
            Filter instructions
            Category explanations
            “How to use the shop” notes
            Background image: wood-background.png
            Text overlays as needed

END OF TABLE 1

🎨 About Image Sizes
        You don’t need the images to be pre‑sized.
        You can safely let CSS do the work:
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        This ensures:
            The blackboards always fill the 300×300 cell
            The shop photo always fills its 300×300 cell
            No stretching or distortion
            No white gaps
            If you later decide to resize the cells (e.g., 320px or 280px), the images will adapt automatically.

🧵 Page Background
        linen-background.jpg is the page background
        Divider cells (4px) are transparent so the linen shows through
        You can swap the background later without touching the tables

🧱 Vertical Buffer Below Table 1
        You now have:
        Table 1
            8px vertical buffer
        Table 3 (Display Window) begins below that
            This is clean and easy for GCP to implement:
            Code
                <div style="height:8px;"></div>
                or a CSS class -- Gpa John prefers NO CSS CLASS.

Image Handling (Updated)
    Since you’re not sure the images are pre‑sized, the safest CSS for all blackboard and photo cells is:
        Code
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        This ensures:
            No stretching
            No white gaps
            Frames always fill the cell
            You can resize cells later without breaking anything

🧱 TABLE 2 — DISPLAY WINDOW (Right‑Side Sticky Sidebar)
    Purpose
        A fixed, non‑scrolling sidebar that always shows the full product card when a thumbnail is clicked.
    Position
        Sits on the right side of the page
        Begins at the top of the viewport, aligned with Table 1
        Does not scroll with the main content
        Independent from Tables 1 and 3
        Outside Margins
            Left margin: 0px (flush against the main content area)
            Right margin: 10px (breathing room from browser edge)
        Width: 320px
            Matches your 300px product card width
            Allows 10px padding on each side
            Visually balanced with the ~910px main area
        Height: auto
            Should extend the full height of the viewport
            Should remain visible as the user scrolls the main table
            Scrolling Behavior: Sticky / fixed
            Does not scroll with the main table
            The product card inside may scroll internally if needed, but the table itself stays put

📐 TABLE STRUCTURE
    Rows
        1 row only
        Height = auto (fills the sidebar)
    Columns
        1 column only
        Width = 320px
    Cell Content
        A single large cell containing:
            A wood‑frame background image (wood-background.png)
            The full product card injected via JavaScript when a thumbnail is clicked
        Optional internal padding (10px recommended)
    Cell Behavior
        Background image fills the cell:
        Code
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            No borders
            No internal table dividers
            No padding unless you choose to add it later

🎨 Visual Notes
    The wood frame gives the display window a “mounted on the wall” feel
    The 320px width keeps the card readable without crowding
    The 10px right margin prevents the sidebar from feeling glued to the browser edge
    The fixed position ensures the display window is always visible while browsing thumbnails

🧱 TABLE 3 — PRODUCT THUMBNAIL / Catalog GRID (Below Table 1)
Purpose: Display 6 thumbnails across, with wood shelf separators
Position: Immediately below Table 1, after the 8px vertical buffer

Total columns: 11 (6 thumbnails + 5 dividers)
    Thumbnail cell width: 150px
    Divider cell width: 4px
    Total width:
        6 × 150 = 900
        5 × 4 = 20
        Total = 920px
            This matches your new Table 1 width logic.

📐 ROW STRUCTURE
    Row 1 — 150px tall (Thumbnails Row A)
    11 columns total
    Pattern:
        Col 1: 150px — Thumbnail 1
        Col 2: 4px — Divider (transparent)
        Col 3: 150px — Thumbnail 2
        Col 4: 4px — Divider
        Col 5: 150px — Thumbnail 3
        Col 6: 4px — Divider
        Col 7: 150px — Thumbnail 4
        Col 8: 4px — Divider
        Col 9: 150px — Thumbnail 5
        Col 10: 4px — Divider
        Col 11: 150px — Thumbnail 6

Thumbnail cell behavior
    Background: product thumbnail image
    Image scaling:
        Code
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            No padding
            No borders

Divider cells
    4px wide
    Transparent
    Show linen page background through them
    
Row 2 — 4px tall (Shelf Row A)
    Same 11‑column structure
        Rowspan NOT needed — this row is the shelf
        Background image: shelf-wood.png (or whatever your shelf plank file is)
        Background behavior:
        Code
            background-size: cover;
            background-repeat: no-repeat;
            background-position: center;
            No borders
            No padding
            No content
.
        This creates the visual “wood shelf” under the first row of thumbnails.

Row 3 — 150px tall (Thumbnails Row B)
    Identical to Row 1:
    6 thumbnails
    5 transparent 4px dividers
    Same scaling rules
    Same column widths
    This is your second row of product thumbnails.
    
Row 4 — 4px tall (Shelf Row B)
        Identical to Row 2:
        Full‑width wood shelf
        4px tall
        Background image fills the row
        No borders, no padding
        This shelf visually closes out Table 2 and prepares the eye for Table 3 or whatever comes next.

🎨 Page Background
    linen-background.jpg sits behind everything
    Divider cells (4px) are transparent so the linen shows through
    Shelf rows override the linen with the wood plank image 

📄 FOOTER
    A shared/common footer to be built will be at page bottom, full screen width, containing links to:
        gpaskids.com
        gpasfaith.com
        gpasshop.com
        and other info -- cookies,  copyright, built by, etc.
    
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
