# PHP Code Snippets

### Table of Contents

**[Most Frequent Word(s) in a String](#most-frequent-words)**

### Most Frequent Words
```php
function most_frequent_words($string, $stop_words = [], $limit = 5) {
	$words = array_count_values(array_diff(str_word_count(strtolower($string), 1), $stop_words)); 
	arsort($words); // Sort based on frequency
	
	return array_slice($words, 0, $limit);
}
```
