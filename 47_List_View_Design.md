# 47. List View Design

## Overview
List view design specifications for displaying collections of data.

## List Features
- **Display:** Show relevant columns for quick scanning
- **Sorting:** Click column header to sort ascending/descending
- **Filtering:** Drop-down filters for quick filtering
- **Search:** Text search across displayed columns
- **Pagination:** Display 50 rows per page with navigation
- **Bulk Actions:** Select multiple rows for bulk operations
- **Export:** Export list to Excel/CSV
- **Grouping:** Group by column (optional)

## Column Selection
- **Key Identifier:** First column (Project ID, PO#, etc.)
- **Status:** Show status prominently
- **Amount/Value:** Show monetary values
- **Date:** Show key dates
- **Owner/Responsible:** Show assigned person
- **Maximum 6-8 columns** (avoid horizontal scroll)

## Filtering Options
- **Status Filter:** Dropdown with status options
- **Date Range:** From/to date pickers
- **Person/Vendor:** Dropdown of people or vendors
- **Amount Range:** Min/max numeric inputs
- **Text Search:** Free-text search box

## Row Actions
- **Default:** Click row to open details
- **Edit:** In-line edit (optional)
- **Delete:** Delete icon with confirmation
- **Print:** Print icon for printable view
- **Email:** Send icon for emailing
- **Custom Actions:** Based on workflow

## Mobile List Design
- **Single Column:** Show only one key column
- **Compact:** Smaller fonts, reduced padding
- **Swipe Actions:** Swipe left for actions
- **Details Link:** Tap row to view details
- **Filters Collapsed:** Show/hide filter options

## Performance
- **Lazy Loading:** Load rows as user scrolls
- **Debounced Search:** Wait for user to stop typing
- **Cached Sorting:** Cache sorted results
- **Index Queries:** Optimize database queries

## Related Documents
[45_Page_and_Screen_Specification.md](45_Page_and_Screen_Specification.md) - Screen layouts
[46_Form_Design.md](46_Form_Design.md) - Form design
