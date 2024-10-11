# Lecture notes, Amibo Project

## Fetching Function from Helper File
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - Created a search input.
  - Initially, the implementation was more DRY, but Jest didn’t like it. As a solution, functionality was moved into functions further down the code.
  
</details>

## Async Function: Fetch and Render
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - Uses `fetchAmibos` with the complete URL and stores it in a constant.
  - The constant is placed into a `renderAmiibo` list, and if it doesn't receive anything, an error message is shown.
  
</details>

## Step 2: Fetching All Amiibos and Creating the Render Function
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - First, we fetch all the amiibos. The next step is to create the render function (Step 2).
  - This function uses the `listView` element from the HTML. It is not declared at the top due to Jest requirements.
  - It loops through the list using `forEach`, creates a `div` element, and assigns a class for the amiibos.
  - A button is added with the class `readMore`, and data attributes `data-head` and `data-tail`.
  - When the button is clicked, the complete data is passed via the event and stored in these data attributes.
  
</details>

## Step 3: Fetch and Render Amiibo Details
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - This step fetches and renders amiibo details.
  - A constant `apiURL` is created, and the ID is extracted.
  - Once the URL is constructed, it is sent to the function in `api.js`.
  - An `if` condition checks if an amiibo exists, and it is then rendered. There is still a lack of error handling.
  - Ideally, you shouldn’t reach the error message, as spaces should be checked earlier.
  
</details>

## Step 4: Details Rendering
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - Renders with `detailsView` and `listView`.
  - DRY principles are broken here due to Jest preferring this approach.
  - If no amiibo is found, an error message is returned. Otherwise, the `innerHTML` is set accordingly.
  - A return statement ensures no empty amiibo is rendered.
  - An event listener is added to the back button, toggling its visibility.
  - Before finishing, the list is hidden, and the details are displayed.
  
</details>

## Step 5: Search Filter
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - The search function is implemented in the simplest way.
  - `searchInput` is declared at the beginning.
  - Every time the event is triggered, it fetches the value, retrieves all amiibo items, and processes them as a node list.
  - It loops through the list, checks the name of each item, and compares it with the search term.
  - If the name matches the search term, the item remains visible; otherwise, it is hidden. This manipulates the display of individual elements.
  
</details>

## Final Steps
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - The final step ensures all content on the page is loaded.
  - Fetches all amiibos initially and implements live search.
  
</details>