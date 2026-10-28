# Session L1 — Team 08

Date: 25/10/2026
Build under test: https://with-bugs.practicesoftwaretesting.com (tab reads "Toolshop - v5.0 with bugs")
Participants: Kudzai Mapfumo (KayJames196), Josiah Macherenga (MrJayZW), Norman Marohwa (NormanMa25), Tadiwanashe Musonza (TadiwanasheMusonza)
Time box: 40 minutes

## Charters

- [Josiah Macherenga] Explore the customer account pages (account home, profile, favorites, invoices, messages) and the contact form, logged in as the demo customer, to discover data-display and validation problems.
- [Kudzai Mapfumo] Explore the shopping cart by adding products, changing quantities, and removing items to discover cart-update and total-calculation problems.
- [Norman Marohwa] Explore product browsing and category navigation to discover missing product information, incorrect category labels, and navigation problems.
- [Tadiwanashe Musonza] Explore the product detail page (Thor Hammer) by adding it to the cart more than once and using the quantity selector and the Add to favourites button to discover add-to-cart rule, error-message and layout problems.

## Product model (from step 1)

- Visitor can: Navigate the home page, browse products by category, view product details, filter and sort products, add products to the cart, and access the contact page.
- Logged-in customer can: Open My account, which links to Favorites, Profile, Invoices and Messages; edit profile details and change password; browse the Categories menu; add products to the cart and proceed to checkout (steps: Cart, Sign in, Address, Payment); and send a message through the Contact form (subject, message, optional TXT/PDF/JPG attachment under 500KB).
- Administrator can: Manage products, categories and brands; view registered users; monitor order statuses; view sales and invoices; and review customer messages.
- Where money appears: Product prices on category pages and product pages, cart price and totals, checkout, and invoice totals on My invoices (in $).
- What this product is for: Selling hand tools, power tools and chainsaws, including rentals, for carpentry and home repairs.

## Session log

Account: customer@practicesoftwaretesting.com / welcome01 (greeted as "Jane Doe" on the contact page). All pages are under with-bugs.practicesoftwaretesting.com/#/ .

| # | Mark | Area | What happened | How to get back to it |
|---|------|------|---------------|-----------------------|
| 1 | ANOMALY | Navigation | The top-right menu shows "User Data not found" instead of the user's name on every logged-in page. The contact page greets the same user as "Hello Jane Doe". | Log in as the customer, look at the top-right of the navigation bar on My account, Profile, Favorites, Invoices, Messages, Contact and the category pages. |
| 2 | ANOMALY | Profile | First Name shows "Doe" and Last Name shows "Jane". The names appear to be swapped because the contact page greets the user as "Jane Doe". | Log in, open My profile (#/account/profile), read the First Name and Last Name fields. |
| 3 | ANOMALY | Profile | The City field contains the text "City not found" instead of a city. Postcode, State and Phone are empty. | Open My profile and look at the City field in the right-hand column. |
| 4 | ANOMALY | Categories | The Categories menu has an entry "UNDEFINED" between Power Tools and Chainsaws. It opens #/category/undefined, titled "Category: Undefined", with no products and nothing under "By category". Its brand filter lists unusual names such as "Brand name 105623523523" and "123". | Open Categories in the top nav, click UNDEFINED. |
| 5 | ANOMALY | Text | The nav link reads "Contakt". The contact form message placeholder reads "Massage". The error message on a product page reads "Oeps, something went wrong." The product page button says "Add to favourites" while the account menu says "favorites". | Look at the top nav on any page; open #/contact; see row 10 for the product-page messages. |
| 6 | ANOMALY | Layout | The logo shows a broken-image icon at the top-left on every page. | Open any page and look at the top-left corner. |
| 7 | ANOMALY | Cart | In the cart (#/checkout, step 1 Cart) the Thor Hammer row shows quantity 1 and price $11.14, but its line Total shows $00.00. The cart Total below shows $11.14. The column above the remove (×) button is also headed "Total". | Log in as the customer, add Thor Hammer (#/product/9) to the cart, open the cart, compare the row Total with the cart Total. |
| 8 | ANOMALY | Profile | After clicking Update Profile, a red banner reading "Resource not found" appears under the button. The form still shows First Name "Doe", Last Name "Jane", Address "Test street 98", City "City not found". [FILL IN: what you changed before clicking, and whether the change was saved after reloading.] | Log in, open My profile (#/account/profile), click Update Profile. |
| 9 | ANOMALY | Categories | Clicking "Chainsaws" in the Categories menu goes to #/chainsaws and shows "404 Error / Page Not Found". Hand Tools (#/category/hand-tools) and Power Tools (#/category/power-tools) open normally. | Open Categories in the top nav and click Chainsaws. |
| 10 | ANOMALY | Product page | With Thor Hammer already in the cart (cart badge shows 1), clicking Add to cart on #/product/9 shows two red messages at once: "You can only have one Thor Hammer in the cart." and "Oeps, something went wrong." The product description says only one Thor Hammer is permitted per customer. | Add Thor Hammer to the cart once, then click Add to cart again on its product page. |
| 11 | ANOMALY | Product page | On the Thor Hammer page the "Add to favourites" button overlaps the "Add to cart" button, so its label reads "dd to favourites". | Open #/product/9 and look at the two buttons under the quantity selector. |
| 12 | ANOMALY | Category pages | On Power Tools, the product names "Belt Sander" and "Random Orbit Sander" are right-aligned, while "Sheet Sander" is left-aligned. | Open Categories, Power Tools (#/category/power-tools), compare the first three product cards. |
| 13 | QUESTION | Invoices | INV-2022000001 and INV-2022000002 are dated 2026-10-24 and 2026-10-26, so the year in the invoice number does not match the date. INV-2020000001 is dated 2020-07-16, but INV-2020000002 is dated 2020-03-20, so number 2 has an earlier date than number 1. Is this expected? | Log in, open My invoices (#/account/invoices), compare invoice numbers with their dates. |
| 14 | QUESTION | Invoices / Profile | Every invoice shows billing address "Test street 123", but the profile address is "Test street 98". It is unclear whether invoices should use the current profile address or keep the address recorded when the invoice was created. | Compare My invoices (Billing Address column) with My profile (Address field). |
| 15 | QUESTION | Account | The My account page says "manage your profile, favorites and orders", but only Favorites, Profile, Invoices and Messages are offered, with no Orders option. | Log in and open My account (#/account). |
| 16 | QUESTION | Category pages | The Sort drop-down on Hand Tools and Power Tools is blank, with no selected option or placeholder. [FILL IN: did you open it, and what options did it show?] | Open Categories, Hand Tools, look at the Sort box above Filters. |
| 17 | NOTE | Messages / Favorites | The Messages page is empty ("There are no messages yet") and links to the contact form. Favorites lists Combination Pliers, Slip Joint Pliers and Belt Sander, with descriptions cut off by "...". | Open My messages (#/account/messages) and My favorites (#/account/favorites). |

## Debrief

1. Covered / not covered:
   Covered (each point has at least one log row or screenshot): the customer account pages (account home, profile, favorites, invoices, messages); the Hand Tools and Power Tools category pages, the UNDEFINED category and the Chainsaws link; the Thor Hammer product page, including adding it to the cart a second time and the Add to favourites button; the first step of the cart (#/checkout); and Update Profile, which returned an error.
   Not covered: registration and login validation (nobody explored them); the Sign in, Address and Payment steps of checkout, so no order was completed; changing cart quantities and removing items (no result was recorded); submitting the contact form (opened, but no submission result recorded); saving a profile change successfully and checking it after a reload; changing the password; filtering by category or brand and using the Sort options on the category pages (the Sort box was only seen blank); the other products and the Rentals category; and all administrator functions. We looked at the product model for the administrator but did not test it.

2. What we found:
   The log has 12 anomalies, 4 questions and 1 note. The most serious are in the cart and the account: the Thor Hammer line total shows $00.00 while the cart total shows $11.14 (row 7), and Update Profile answers "Resource not found" (row 8), so a customer may not be able to change their details. The Chainsaws category gives a 404 and an "UNDEFINED" category is shown in the menu (rows 4 and 9), so part of the catalogue cannot be browsed properly. "User Data not found" appears in the navigation on every logged-in page (row 1), and the profile shows the first and last names swapped and "City not found" in the City field (rows 2 and 3). The rest are text and layout problems (rows 5, 6, 11, 12). The four questions (rows 13 to 16) are things we could not judge without knowing the intended behaviour.

3. What got in the way:
   Four areas had to be explored by four people inside one 40-minute time box, so each area got a short look rather than a deep one. Several problems also blocked the exploring itself: the "Resource not found" error meant we could not tell whether profile changes are saved, the 404 and the empty UNDEFINED category meant those categories could not be browsed, and the one-per-customer rule on the Thor Hammer meant we could not try larger quantities of that product. Without the requirements we could not tell whether the invoice numbering, the invoice billing address and the blank Sort box were intended, so we logged them as questions instead of anomalies.

4. What we learned:
   The same kind of fault, missing or placeholder data ("User Data not found", "City not found", "UNDEFINED", "Brand name 105623523523"), shows up in unrelated places, which suggests the data behind several screens is incomplete rather than each screen being faulty separately. Comparing two screens showed the difference: the contact page greets "Jane Doe" while the navigation says "User Data not found". We learned that the cart can show a correct overall total next to a wrong line total, so both must be checked, and that the product page can show a correct rule message together with a wrong generic one. We also learned that some observations (rows 13 to 16) need the intended behaviour confirmed before they can be reported as defects next week.

5. Next charter should be:
   Explore registration and login with invalid details, empty fields and wrong credentials to discover validation and account-access problems, since nobody covered them. After that: explore the cart with quantity changes, removal and repeated adds through to the Sign in step of checkout, and the profile update and contact form with valid and invalid input, checking whether changes persist after a reload.
