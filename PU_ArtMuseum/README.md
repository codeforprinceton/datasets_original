# Info

- [Princeton University Art Museum](http://artmuseum.princeton.edu) (PUAM)

- [Museum Collections](http://artmuseum.princeton.edu/fr/collections)

- Museum's [Image use and Access](http://artmuseum.princeton.edu/image-use-and-access) Info
    + "Thumbnail-sized images of copyrighted works are displayed under fair use"

- [Advanced Search](http://artmuseum.princeton.edu/fr/search/collections-advanced#advanced) page has full lists of classifcations etc used in the data file

- [Mobile App](http://artmuseum.princeton.edu/fr/about/press-room/announcement/princeton-university-art-museum-debuts-first-mobile-app) for one of their exhibitions

- Sample art: row 1 in handbookobjects.csv is a painting called "Annunciation" found here:
http://artmuseum.princeton.edu/fr/collections/objects/18583

- The Artist (da Siena) is found here:
http://artmuseum.princeton.edu/fr/collections/maker/5010


# Data Columns: Contents, Issues and Questions

## puamdata_handbookobjects.csv
This is a table of art objects with maker, title, era, medium, size, donor, classification and photo information.

### ObjectID
- type: number
- description: internal PUAM number, used in item's URL in online collection, it's the last part of object's URL path

### Object Number
- type: string
- format: mostly contain a prefix, year and identifier; some prefixed 'x' and some 'y' and some without any prefix.
- description: another unique identier, probably pre-digital

### Sort Number
- type: string
- format: similar to Object number but with the prfix moved to the end of the string
- description: an identifier that will sort correctly alphanumerically, correlates with the Object Number field

### Dept
- type: string
- description: short string that indicates which part of the museum the piece is in. Examples: American, African, Photo, etc. Also contains the following abbreviations: 
    + AAA: Art of the Ancient Americas
    + ABI: Ancient, Byzanntine and Islamic
    + EPS: European
    + Moco: Modern and Contemporary
    + P&D: Prints and Drawings
    + Photoarch: Photo Archives
- TODO: make these choices into a data list somewhere. Note that even values like 'American' are short for 'American Art' - e.g. each has a short and long name values

### Maker
- type: string
- description: what person or culture created the piece

### Alpha Sort
- type: string
- description: same as Maker but listed last name first for sorting 

### Title
- type: string
- description: name of the piece

### Date
- type: string 
- description: human readable dates like '240 B.C' or 'ca. 1750'

### Begin Date
- type: number
- description: machine readable BEGIN date of 'Date' field's range, B.C. dates are negative

### End Date
- type: number
- description: machine readable END date of 'Date' field's range, B.C. dates are negative

### Medium
- type: string
- description: what the art is made of or on or with; seems like a precise list of possible values

### Dimensions
- type: string
- description: size of the piece in both cm and inches; human readable, parsable if cleaned but format changes depending on how many dimensions, oddities, etc

### Credit Line
- type: string
- description: text of the line below the piece crediting the origin of the donation or the loan

### ClassificationTerm
- type: list of strings
- description: comma separated list of well known terms for what the piece is: drawings, watercolors, oil paintings, etc.

### Copyright
- type: string
- description: blank but for two entries with a copyright assigned to the PU trustees

### Photo Credit
- type: string
- description: who took the museum's picture for them. Parseable. Some blanks.

### Primary Image URL
- type: link
- description: URL to the image.
- NOTE: not a thumbnail picture, quite large! Missing protocol portion of URL. 
- NOTE: there are thumbnails on the website, likely can figure out their URL and it will be similar
- NOTE: image file name seems derived from Object Name field.

### Primary Image Filename
- type: string
- description: file name portion of the image URL

## puamdata_handbookobjects.csv
This is a table of the art objects' geographic information. Geo info is only very approximate.

- TODO: check this out in more detail. Well, actually there isn't much there.


# Possible Projects

- simply provide a REST API to the data for others to re-use
- iOS app for browsing?
- if more detailed location information was available map the art with Google Maps
- 