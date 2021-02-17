# php search system like google
Search System in PHP like Google


<?php
    $search = 'my name is krishna';

    $searchSplit = explode(' ', $search);

    $searchQueryItems = [];
    foreach ($searchSplit as $searchTerm) {
        $searchQueryItems[] = "name LIKE '%" . mysqli_real_escape_string($searchTerm) . "%'";
    }

    $query = 'SELECT * FROM table_name' . (!empty($searchQueryItems) ? ' WHERE ' . implode(' AND ', $searchQueryItems) : '');
?>
