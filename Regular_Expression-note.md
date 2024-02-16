# Regular Expression - *Regex*
*[Course Link](https://www.youtube.com/playlist?list=PL4cUxeGkcC9g6m_6Sld9Q4jzqdqHd2HiD "Link here")*  
*[github](https://github.com/iamshaunjp/regex-playlist)*
- **Online Tool**
  - **[Regex 101](https://regex101.com/ "Link here")** - test
  - **[Regexr](https://regexr.com/ "Link here")** - search rule
- **Rule**
  - ```^```
    - regex中，^可代表*開頭*或*否定*
      - 開頭 - ^ 在表達式開頭通常代表字符串的開頭  
        ```^Hello```
      - 否定 - 在方括號內通常代表否定。例如以下匹配不以大寫字母開頭的字符串：
        ```^[^A-Z]```
  - ```[a-z]``` - match single character between a to z
  - white-space
    - ```\s``` - matches any whitespace character (spaces, tabs, line breaks).
    - ```\S``` - matches any character that is not a whitespace character (spaces, tabs, line breaks).
  - ```\d``` - matches any digit character (0-9). Equivalent to [0-9].
  - ```\t``` - matches a tab character only
  - word character
    - ```\w``` - matches any word character (alphanumeric & underscore). Equivalent to ```[A-Za-z0-9_]```
    - ```\W``` - matches any that is not word character (alphanumeric & underscore). Equivalent to ```[^A-Za-z0-9_]```
  - ```.``` - matches any character except linebreaks. Equivalent to ```[^\n\r]```.
  - ```^``` - begin  
    ```$``` - end
  - ```+``` - matches 1 or more of the preceding token. e.g. ```b\w+ matches be bee beer beers```
  - ```*``` - matches 0 or more of the preceding token. e.g. ```b\w+ matches b be bee beer beers```
  - ```{1,3}``` - matches the specified quantity of the previous token. ```{1,3}``` will match 1 to 3. ```{3}``` will match exactly 3. ```{3,}``` will match 3 or more. e.g. ```b\w{2,3} matches bee beer beers```
  - ```?``` - matches 0 or 1 of the preceding token, effectively making it optional. e.g. ```colou?r matches color colour```
  - ```|``` - Acts like a boolean OR. Matches the expression before or after the |. e.g. ```b(a|e|i)d matches bad bed bid```
  - ```(pet|toy|crazy) rabbit``` - matches ```pet rabbit```
- Regex in javascript
  - ```var reg = /[a-z]/ig;```  
    ```var reg2 = new RegExp(/[a-z]/, 'g');```
  - telephone no.  
    ~~~ javascript
      const inputs = document.querySelector('input');
      const patterns = {
        telephone: /^\d{11}$/,
        username: /^[a-z\d]{5,12}$/i,
        password: /^[\d\w@-]{8,20}$/i,
        slug: /^[a-z\d-]{8,20}$/,
        email: /^([a-z\d\.-]+)@([a-z\d-]+)\.([a-z]{2,8})(\.[a-z]{2,8})?$/
        // yourname @ domain   .  com          ( .uk )

      };
      // validation function
      function validate(field, regex){
          if(regex.test(field.value)){
              field.className = 'valid';
          } else {
              field.className = 'invalid';
          }
      }

      inputs.forEach((input) => {
        input.addEventListener('keyup', (e) => {
          // console.log(patterns[e.target.attributes.name.value]);
          validate(e.target, patterns[e.target.attributes.name.value]);
        });
      });
    ~~~
    
