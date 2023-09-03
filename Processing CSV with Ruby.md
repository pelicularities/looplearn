#ruby #csv #cheatsheet 

```ruby
require 'csv'

# Read CSV file into 2D array
file = File.read('filename.csv')
data = CSV.parse(file)

# Equivalent to the above
data = CSV.read('filename.csv')

# Parse with headers
data = CSV.parse(file, headers: true)

# Use tabs as column separator
data = CSV.parse(file, col_sep: "\t")
```

## Resources
- [Ruby Documentation: CSV](https://ruby-doc.org/stdlib-3.0.0/libdoc/csv/rdoc/CSV.html)
	- [::read](https://ruby-doc.org/stdlib-3.0.0/libdoc/csv/rdoc/CSV.html#method-c-read)
	- [::readlines](https://ruby-doc.org/stdlib-3.0.0/libdoc/csv/rdoc/CSV.html#method-c-readlines)
	- [::parse](https://ruby-doc.org/stdlib-3.0.0/libdoc/csv/rdoc/CSV.html#method-c-parse)
	- [::parse_line](https://ruby-doc.org/stdlib-3.0.0/libdoc/csv/rdoc/CSV.html#method-c-parse_line)
	- [Options for Parsing](https://ruby-doc.org/stdlib-3.0.0/libdoc/csv/rdoc/CSV.html#class-CSV-label-Options+for+Parsing)
- [Ruby Guides: How to Read & Parse CSV Files with Ruby](https://www.rubyguides.com/2018/10/parse-csv-ruby/)