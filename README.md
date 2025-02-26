
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
