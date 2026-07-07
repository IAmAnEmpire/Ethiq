# Ethiq

**The humane grocery scanner.** Scan a supermarket barcode and see how the animals behind the product were treated. Welfare first, climate second, and never averaged into one misleading number.

Built for the [Futurekind](https://www.electricsheep.is/futurekind) fellowship.

## What it does

Point your phone camera at any EAN or UPC barcode (or type the digits) and Ethiq returns:

- A **welfare grade from A to E** (0 to 100), based on how the animals were farmed.
- The **specific signal** that produced the grade, whether a certified label, the EU egg code, or an inferred species prior.
- **Hours of pain**, broken into the four intensity tiers used by welfare science (annoying, hurtful, disabling, excruciating), so the grade connects to something real.
- A **separate environment grade**, shown side by side and never blended into the welfare score.
- A **source link on every grade**, so anyone can check where the number came from.

## Why welfare and environment are kept separate

Intensive farming often produces lower emissions per kilo than higher-welfare extensive systems. Caged-hen eggs, for example, can score better on carbon than free-range. Collapsing welfare and climate into a single grade would quietly punish the higher-welfare choice, so Ethiq refuses to do it and shows the two scores independently.

## How the grade is built

The scoring engine works in layers, most precise first:

1. **No animal ingredients** scores 100 by construction.
2. **EU egg farming-method code** (mandatory on every carton): 0 organic, 1 free-range, 2 barn, 3 caged.
3. **Certified welfare labels** (Beter Leven, Haltungsform, Étiquette Bien-Être Animal, RSPCA Assured, Label Rouge, GAP, Certified Humane, Animal Welfare Approved, organic schemes) mapped to a published tier crosswalk.
4. **Species priors** as a last resort, clearly flagged as inferred rather than certified.

Grades are estimates for education, not certification.

## Data sources

- Product data: [Open Food Facts](https://openfoodfacts.org) (ODbL license)
- Pain-hour estimates: [Welfare Footprint Institute](https://welfarefootprint.org)
- Certification tier mapping: syntheses from CIWF, the Animal Welfare Institute, and the ASPCA
- Egg farming-method codes: EU Regulation 2023/2465
- Environment grade: Green-Score, derived from Agribalyse and Poore & Nemecek (2018)

## Running it

Ethiq is a single self-contained `index.html` file with no build step and no backend. Open it in a browser, or host it anywhere that serves static files over HTTPS (HTTPS is required for the phone camera to work).

## Missing a product?

If a scan comes back empty, the product isn't in Open Food Facts yet. [Add it there](https://world.openfoodfacts.org/contribute) with a couple of photos and Ethiq will recognise it too, along with every other tool built on the same open database.

## Status

Early prototype. The MVP focuses on eggs, where the EU code gives mandatory, reliable welfare data, and expands outward from there. Feedback and contributions welcome.
