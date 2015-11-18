# Standard PHP functions, implemented for UTF-8 encoding string #

Alphabetical order list:

  1. array\_change\_key\_case()
  1. chr() — Converts a UNICODE codepoint to a UTF-8 character
  1. chunk\_split()
  1. ltrim()
  1. ord() — Converts a UTF-8 character to a UNICODE codepoint
  1. preg\_match\_all() — Call preg\_match\_all() and convert byte offsets into character offsets for PREG\_OFFSET\_CAPTURE flag. This is regardless of whether you use /u modifier.
  1. range()
  1. rtrim()
  1. str\_pad()
  1. str\_split()
  1. strcasecmp()
  1. strcmp()
  1. stripos()
  1. strlen()
  1. strncmp()
  1. strpos()
  1. strrev()
  1. strspn()
  1. strtolower(), lowercase() is alias
  1. strtoupper(), uppercase() is alias
  1. strtr()
  1. substr()
  1. substr\_replace()
  1. trim()
  1. ucfirst()
  1. ucwords()


# Extra useful functions for UTF-8 encoding string #

Alphabetical order list:

  1. **blocks\_check()**<br>Check the data in UTF-8 charset on given ranges of the standard UNICODE.<br>The suitable alternative to regular expressions.<br>
<ol><li><b>convert_case()</b><br>Конвертирует регистр букв в данных в кодировке UTF-8.<br>Массивы обходятся рекурсивно, при этом конвертируются только значения в элементах массива, а ключи остаются без изменений.<br>
</li><li><b>convert_files_from()</b><br>Recode the text files in a specified folder in the UTF-8<br>In the processing skipped binary files, files encoded in UTF-8, files that could not convert.<br>
</li><li><b>convert_from()</b><br>Encodes data from another character encoding to UTF-8.<br>
</li><li><b>convert_to()</b><br>Encodes data from UTF-8 to another character encoding.<br>
</li><li><b>diactrical_remove()</b><br>Remove combining diactrical marks, with possibility of the restore<br>Удаляет диакритические знаки в тексте, с возможностью восстановления (опция)<br>
</li><li><b>diactrical_restore()</b><br>Restore combining diactrical marks, removed by diactrical_remove()<br>Восстанавливает диакритические знаки в тексте, при условии, что их символьные позиции и кол-во символов не изменились!<br>
</li><li><b>from_unicode()</b><br>Converts a UNICODE codepoints to a UTF-8 string<br>
</li><li><b>has_binary()</b><br>Check the data accessory to the class of control characters in ASCII.<br>
</li><li><b>html_entity_decode()</b><br>Convert all HTML entities to native UTF-8 characters<br>
</li><li><b>html_entity_encode()</b><br>Convert special UTF-8 characters to HTML entities.<br>
</li><li><b>is_ascii()</b><br>Check the data accessory to the class of characters ASCII.<br>
</li><li><b>is_utf8()</b><br>Returns true if data is valid UTF-8 and false otherwise. For null, integer, float, boolean returns TRUE.<br>
</li><li><b>preg_quote_case_insensitive()</b><br>Make regular expression for case insensitive match<br>
</li><li><b>str_limit()</b>, <b>truncate()</b><br>Обрезает текст в кодировке UTF-8 до заданной длины,	причём последнее слово показывается целиком, а не обрывается на середине.	Html сущности корректно обрабатываются.<br>
</li><li><b>strict()</b><br>Strips out device control codes in the ASCII range.<br>
</li><li><b>textarea_rows()</b><br>Calculates the height of the edit text in <code>&lt;textarea&gt;</code> html tag by value and width.<br>
</li><li><b>to_unicode()</b><br>Converts a UTF-8 string to a UNICODE codepoints<br>
</li><li><b>unescape()</b><br>Decodes a string to UTF-8 string from some formats (can be mixed)<br>Examples<br>
<pre><code>'%D1%82%D0%B5%D1%81%D1%82'        =&gt; "\xD1\x82\xD0\xB5\xD1\x81\xD1\x82"  #binary (regular)<br>
'0xD182D0B5D181D182'              =&gt; "\xD1\x82\xD0\xB5\xD1\x81\xD1\x82"  #binary (compact)<br>
'%u0442%u0435%u0441%u0442'        =&gt; "\xD1\x82\xD0\xB5\xD1\x81\xD1\x82"  #UCS-2  (U+0 — U+FFFF)<br>
'%u{442}%u{435}%u{0441}%u{00442}' =&gt; "\xD1\x82\xD0\xB5\xD1\x81\xD1\x82"  #UTF-8  (U+0 — U+FFFFFF)<br>
</code></pre>
</li><li><b>unescape_request()</b>
<ol><li>Corrects the global arrays <code>$_GET</code>, <code>$_POST</code>, <code>$_COOKIE</code>, <code>$_REQUEST</code>, <code>$_FILES</code> decoded values from <code>%XX</code> and extended <code>%uXXXX</code> / <code>%u{XXXXXX}</code> format, for example, through an outdated javascript function escape(). Standard PHP5 cannot do it.<br>
</li><li>Recode <code>$_GET</code>, <code>$_POST</code>, <code>$_COOKIE</code>, <code>$_REQUEST</code>, <code>$_FILES</code> from <code>$charset</code> encoding to UTF-8, if necessary. A side effect is a positive protection against XSS attacks with non-printable characters on the vulnerable PHP function. Thus web forms can be sent to the server in 2-encoding: <code>$charset</code> and UTF-8. For example: <code>?тест[тест]=тест</code>
</li><li>If in the HTTP_COOKIE there are parameters with the same name, takes the last value (as in the QUERY_STRING), not the first.<br>
</li><li>Creates an array of <code>$_POST</code> for non-standard Content-Type, for example, "Content-Type: application/octet-stream". Standard PHP5 creates an array for "Content-Type: application/x-www-form-urlencoded" and "Content-Type: multipart/form-data".<br>Examples<br>
<pre><code>'%F2%E5%F1%F2'                    =&gt; 'тест'  #CP1251 (regular)<br>
'0xF2E5F1F2'                      =&gt; 'тест'  #CP1251 (compact)<br>
'%D1%82%D0%B5%D1%81%D1%82'        =&gt; 'тест'  #UTF-8 (regular)<br>
'0xD182D0B5D181D182'              =&gt; 'тест'  #UTF-8 (compact)<br>
'%u0442%u0435%u0441%u0442'        =&gt; 'тест'  #UCS-2 (U+0 — U+FFFF)<br>
'%u{442}%u{435}%u{0441}%u{00442}' =&gt; 'тест'  #UTF-8 (U+0 — U+FFFFFF)<br>
</code></pre>