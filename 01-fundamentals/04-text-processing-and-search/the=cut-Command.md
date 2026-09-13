# The cut Command

*Date: 16 February 2026*

cut is used to extract and analyze specific parts of a file's content.

## Basic Field Extraction

Say we have a customer file like:
```
ID,Name,Age,Email
1,Lamin Jarju,25,lamin.jarju@email.com
2,Fatou Ceesay,35,fatou.ceesay@email.com
3,Ebrima Sanneh,30,ebrima.sanneh@email.com
4,Awa Touray,22,awa.touray@email.com
```

To pull out just the names:
```
cut -d ',' -f 2 theFileName
```

- cut -- the command
- -d ',' -- comma is the delimiter separating fields
- -f 2 -- extract the second field
- theFileName -- input file path

(source: labex.io -- linux cut command lab)

## Skipping the Header Row

```
cut -d ',' -f 2 theFileName | tail -n +2
```

- cut extracts the names field, same as above
- tail -n +2 starts output from the second line, skipping the header

Breaking down tail -n +2: tail normally shows the last few lines of a file, but adding + before the number flips that -- instead of "last N lines," it means "start printing from line N to the end." So +2 means "start from line 2 onward."

## Extracting Multiple Fields

```
cut -d ',' -f 2,3 theFileName
```
Pulls out the name and age fields together.

## Extracting a Range of Fields

```
cut -d ',' -f 1-3 theFileName
```
Grabs the first three fields.

## Fixed-Width Fields (No Delimiter)

Sometimes data isn't separated by a delimiter at all -- it's laid out in fixed-width columns instead. cut can still handle this with the -c option, specifying character positions.

Example, extracting characters 11-25 from each line:
```
cut -c 11-25 theFileName
```
This pulls out just the title field from fixed-width inventory data, since that field happens to sit in that character range.

## Combining cut with grep

```
grep -E ',[2-9][0-9]\.[0-9]{2}$' theFileName | cut -d ',' -f 2
```

- grep -E ',[2-9][0-9]\.[0-9]{2}$' -- regex matching lines where the price is $20 or more (comma, then 20-99, decimal point, two more digits, end of line)
- cut -d ',' -f 2 -- pulls out just the title field from whatever grep matched

## Other Options Worth Knowing

- -s -- suppress lines that don't contain the delimiter at all
- --output-delimiter=STRING -- use a custom delimiter in the output
- --complement -- select everything EXCEPT the specified fields/characters