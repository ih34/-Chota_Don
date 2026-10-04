# Meesho Rozana prototype

Customer-side prototype for **Meesho Rozana**, Team Moodlers' entry in the Meesho DICE Challenge Season 3 (Business Track, "Winning Male Users on Meesho").

Rozana is a list-led essentials shopping experience inside the Meesho app for budget-conscious shoppers in Tier 2 and Tier 3 cities: household men doing the weekly or monthly restock, students and working professionals with little time and a tight budget. Everything is matched to products already on Meesho at prices shown against MRP, delivered through Meesho's standard fulfilment.

## What the prototype does

- **Rozana List**: a tick list of household essentials, bath and grooming, and school and stationery items with a weekly or monthly cadence. Tick what you need this cycle, untick what you still have, add the ticked items to the cart in one tap. Ready-made starter lists for the three personas.
- **Snap-a-List**: photograph or upload a paper shopping list. Each recognised line gets two or three matching products with the Meesho price against MRP; pick one per line. Lines with no match go to a separate "not available on Meesho yet" list. (Text recognition is simulated in the prototype; the sample list stands in for the OCR output. Matching, pricing and availability run for real on the in-app catalogue.)
- **Checkout guard**: anything ticked on the list but missing from the cart is shown at checkout with Add or Skip.
- **Seller comparison**: the same product compared across Meesho Mall and verified sellers; verification and ratings as the trust signal.
- **Smart add-ons**: at most two contextual suggestions at cart, never ranked above the customer's own items, one-tap dismiss.
- **Order lifecycle**: delivery date shown before paying, tracking (packed, shipped, out for delivery, delivered), one-tap returns for 7 days.
- **Refill loop**: reminder tied to the list cadence, one-tap reorder, savings against MRP on every order.

State persists in the browser (`localStorage`), so a returning visitor continues as the same customer. The slim bar at the bottom holds three demo controls: mark delivered, jump 26 days ahead, reset.

## Files

```
index.html            the whole app as one self-contained file (built output)
src/app.js            application logic and screen templates
src/phone.css         in-app styles
src/template.html     page shell; build.py inlines css, js and the logo into it
assets/               Meesho logo (full size and the 96 px version used in the build)
wireframes/           screens-only PDF of the twelve screens
scripts/build.py      rebuild index.html from src/ and assets/
scripts/wireframes.js render the screens to wireframes/wireframes.html
scripts/pdf.py        turn that HTML into the PDF
vercel.json           static hosting config
```

## Run it

Open `index.html` in a browser. No build step and no server required.

To host it, drop the folder on Vercel, Netlify or GitHub Pages; it is a static site with a single file.

```bash
npx vercel --prod
```

## Rebuild after editing

```bash
python3 scripts/build.py          # src/ -> index.html
node scripts/wireframes.js        # screens -> wireframes/wireframes.html
python3 scripts/pdf.py            # -> wireframes/Rozana-Wireframes.pdf
```

The PDF scripts need Node, Python 3, `pip install playwright pypdf` and `playwright install chromium`.

## Notes

- Brand colours: Meesho purple `#9F2089`, deep purple `#580A46`, yellow `#FF9D00`. Mulish is used as a stand-in for Meesho's Mier B typeface, which is not freely available.
- Prices, sellers and ratings are illustrative placeholders for the prototype.
- The Meesho name and logo belong to Meesho; they are used here only for a competition entry.

Team Moodlers, IIT (BHU) Varanasi.
