# Grep for Web Devs
A grep cheat sheet that any Web Developer can understand.

# How do I use regular expressions similar to PHP's `preg_*` functions?
```
grep -P
```
The `-P` flag will give you PCRE (Perl Regular Expressions) which is the same syntax that PHP uses.

## Example
```
echo '123' | grep -P '\d{3}' # will match
```

# How do I use regular expressions similar to Javascript's `.match()` syntax? 
```
grep -P
```

# How do I recursively look through a folder?
```
grep -R
```
## Example
```
# Search through /var/www/html for the phrase 'preg_replace'
grep -R preg_replace /var/www/html
```

# Okay, I can search through a directory, but I'm getting lots of giant compiled javascript. How do I ignore those?
This varies depending on your chosen stack because compiled assets can show up anywhere.
*Usually*, people want to ignore minified css/js assets.
You'll want to use `--exclude=pattern'

To ignore minified css and minified js:
```
grep -R --exclude='*.min.css' --exclude='*.min.js' /var/www/html
```

# How do I get color *and* pipe through `less`?
You'll want to use:
```
grep --color=always | less -R
```

## Example
```
grep -R preg_replace --color=always /var/www/html | less -R
```
