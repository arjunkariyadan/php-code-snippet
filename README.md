# PHP Code Snippets

### Table of Contents

- [Most Frequent Word(s) in a String](#most-frequent-words-in-a-string)

### Most Frequent Word(s) in a String
most_frequent_words — Find most frequent word(s) appeared in a String
```php
function most_frequent_words($string, $stop_words = [], $limit = 5) {
    $string = strtolower($string); // Make string lowercase

    $words = str_word_count($string, 1); // Returns an array containing all the words found inside the string
    $words = array_diff($words, $stop_words); // Remove black-list words from the array
    $words = array_count_values($words); // Count the number of occurrence

    arsort($words); // Sort based on count

    return array_slice($words, 0, $limit); // Limit the number of words and returns the word array
}
```
Returns array contains word(s) appeared most frequently in the string.

Parameters :

string $string - The input string.

array $stop_words (optional) - List of words which are filtered out from the array, Default empty array.

string $limit (optional) - Limit the number of words returned, Default 5.
