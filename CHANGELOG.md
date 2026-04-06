# Distribution Calculator Changelog

## 2026-04-06 - Walkway GSM-specific pricing
- Updated Walkway Remote, Express, and Express Remote with correct 157gsm and 260gsm pricing
- Previously all three GSM tiers used the same 128gsm values
- Each walkway type now has unique tier tables and above-4-slot rates per GSM

## 2026-04-06 - HDB Letterbox tier pricing
- Replaced flat per-1K letterbox pricing with full tier table (1K-10K)
- Letterbox price = HDB Door-to-Door Standard minus $2 per 1K qty
- Supports all sizes (A5, A4, A3) and all GSMs (128, 157, 260)
- Above 10K uses per-1K rate (also Standard rate minus $2)
- Removed sub-types (no Estate/Selected Blocks for letterbox)

## 2026-04-06 - MOQ floor for Multiple Flyer
- Minimum charge for multiple flyer tier pricing is the 1K tier price
- Prevents tagalong discount from dropping below base price (e.g., 500+500 = $149 not $139)

## 2026-04-06 - Multiple Flyer: combine quantities for tier lookup
- For designs with < 3K qty each, combine quantities for single tier lookup
- e.g., 1K + 1K = 2K tier ($177 - $10 = $167)
- e.g., 2K + 2K = 4K tier ($212 - $10 = $202)

## 2026-04-06 - Multiple Flyer: tier-based pricing for < 3K
- Quantities below 3K now use tier prices instead of per-1K rates
- e.g., 2K = $177 (not 2 x $38 = $76)

## 2026-04-06 - Multiple Flyer: tagalong threshold fix
- Tagalong discount ($10/1K off) now applies when 1st design qty >= 5K (was 10K)

## 2026-04-06 - Multiple Flyer Per Unit feature
- New add-on: specify number of flyer designs with individual Size, GSM, Qty
- Uses highest GSM across all designs for rate lookup
- 1st flyer: full rate, 2nd+ flyers: tagalong discount ($10/1K off at 5K+)

## 2026-04-06 - Prorate function fixes
- Fixed undefined `hi` variable (changed to `tiers[i][sizeIdx]`)
- Fixed wrong tier rate: proration now uses previous tier rate, not always 1K tier
- e.g., 2005 units now correctly calculates as $177.44 (not $194)
