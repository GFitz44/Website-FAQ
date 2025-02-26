<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple jQuery Search</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
        .hidden { display: none; } /* Class to hide unmatched items */
    </style>
</head>
    <script>
        $(document).ready(function() {
            // Listen for input changes in the search field
            $("#searchInput").on("keyup", function() {
                // Get the search term, convert to lowercase for case-insensitive matching
                var searchTerm = $(this).val().toLowerCase();

                // Loop through each item in the content area
                $("#content p").each(function() {
                    // Get the text of the current item, also lowercase
                    var itemText = $(this).text().toLowerCase();

                    // Check if the search term is in the item's text
                    if (itemText.indexOf(searchTerm) === -1) {
                        // If no match, hide the item
                        $(this).addClass("hidden");
                    } else {
                        // If match, show the item by removing the hidden class
                        $(this).removeClass("hidden");
                    }
                });
            });
        });
    </script>

<body>
    <h2>Search Example</h2>
    <input type="text" id="searchInput" placeholder="Type to search...">
    <div id="content">
        <p>Apple pie is delicious.</p>
        <p>Bananas are yellow and sweet.</p>
        <p>Cherries grow on trees.</p>
        <p>Dates are sticky and brown.</p>
    </div>

    
</body>
</html>
