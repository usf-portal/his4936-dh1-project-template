# Workflow

Describe your overall workflow here.

Discuss (in detail) the processes of

* Getting the data
* Cleaning/altering the data
* Visualizing the data
* Discussing and sharing results with group members

To make elegant workflow charts, use [LucidChart](https://lucidchart.com)

![Workflow Chart of our project](docs\files\project-easter-rising.png)

*A condensed workflow for the project*

Step by Step Processes:  
This section is to show how our team used the data we found and how we went about creating the dataset, visualizations, tables, etc.
Gathering Data: Our group had looked at into scraping websites and archives trying to collect and create datasets that could be used in an excel spreadsheet. The excel spreadsheet could then be used as our base for our research and help direct the vision of our project. Luckily, we were fortunate enough to find a premade excel spreadsheet concerning the people involved in the Easter Rising of 1916. However, this excel spreadsheet was incomplete. The CSV file was still used for the project, but it led to our group finding a PDF with a more complete list of names, but with less in-depth information about the people on the list.


Code for scraping the PDF from the Glasnevin Cemetery trust website (graciously provided by Professor Thomas):
```
import csv



class RecordParser:

    """Gets raw text of a single entry and provides methods to extract data."""

    data = ''



    def __init__(self, raw_text):

        self.data = raw_text



    def __str__(self):

        """Sets self.data as the value for printing and representation in string format"""

        return self.data



    def __repr__(self):

        """Full object info is same as __str__"""

        return self.__str__



    def get_text_between(self, substring_a, substring_b=None):

        """Given two substrings, gets the text between them"""

        # start 1 position after the first substring ends

        start_index = self.data.find(substring_a) + len(substring_a) + 1

        end_index = None

        # if no second substring supplied, make end_index the end of the text

        if not substring_b:

            end_index = len(self.data)

        # otherwise set it to one less than the start of the second substring

        else:

            end_index = self.data.find(substring_b) - 1

        # return the the text between indices from self.data

        return self.data[start_index:end_index]



    def id_num(self):

        """Get id number from raw record, replace any endlines accidentally grabbed."""

        # gets all text after affiliation data

        return self.get_text_between(self.affiliation()).replace('\n', '')



    def initials(self):

        """Get initials from raw record, replace any endlines accidentally grabbed."""

        return self.get_text_between('Initials (Grave Record)', 'Forename (Grave Record)').replace('\n', '')



    def forename(self):

        """Get initials from raw record, turn into normal case, replace any endlines accidentally grabbed."""

        return self.get_text_between(

            'Forename (Grave Record)', 'Surname (Grave Record)'

        ).replace('\n', '').title()



    def surname(self):

        """Get surname from raw record, turn into normal case, replace any endlines accidentally grabbed."""

        return self.get_text_between(

            'Surname (Grave Record)', 'Date of Death (Grave Record)'

        ).replace('\n', '').title()



    def death_date(self):

        """Get death_date from raw record, replace any endlines accidentally grabbed."""

        return self.get_text_between('Date of Death (Grave Record)', 'Affiliation').replace('\n', '')



    def affiliation(self):

        """Get affiliation from raw record, replace any endlines accidentally grabbed."""

        # since affiliation can't use a following 'header' to locate, look only in text after 'Affiliation'

        search_text = self.data[self.data.find('Affiliation') + 12:]

        possible_affiliations = [

            'Civilian',

            'British Army',

            'Irish Volunteers',

            'Irish Citizen Army',

            'Irish Association of Volunteer Training Corp',

            'Royal Irish Constabulary'

        ]

        # if affiliation is found in text, return it

        for possible_affiliation in possible_affiliations:

            if possible_affiliation in search_text:

                return possible_affiliation

        # if no match found, return Uncertain

        return 'Uncertain'



    def parse(self):

        return {

            'ID': self.id_num(),

            'Initials': self.initials(),

            'Forename': self.forename(),

            'Surname': self.surname(),

            'Death Date': self.death_date(),

            'Affiliation': self.affiliation()

        }





# === Main Script ===



# make blank list to store records and open file with raw data

raw_records = []

with open('Glasnevin.txt', mode='r+', encoding='latin_1') as rawfile:

    # read file data and use double endlines to split into list of raw records

    raw_records = rawfile.read().split('\n\n')



# make blank list for processed records, loop through each raw record, parse it, and append

records = []

for raw_record in raw_records:

    parser = RecordParser(raw_record)

    records.append(parser.parse())



# open file to output parsed csv

with open('Glasnevin.csv', mode='w+', encoding='latin_1') as csvfile:

    # declare csv header columns, create writer object, and write the header row to file

    fieldnames = ['ID', 'Initials', 'Forename', 'Surname', 'Death Date', 'Affiliation']

    writer = csv.DictWriter(csvfile, fieldnames=fieldnames)

    writer.writeheader()

    # loop through each record and write csv rows

    for record in records:

        writer.writerow(record)



print('Successfully exported to Glasnevin.csv')
```
