# SeismicStations

## ~/src/SeismicStations

Scripts and data for seismic stations.

## Description

This is a long-standing personal project to work with information about seismic stations. It's a sort-of relational database that stores data in CSV text files, with pipe-able scripts to extract that data.

Some bits of it don't work or are incompletely implemented.

The *unicsv* file format for *gpsbabel* uses tabs!

## Usage

### Dependencies
* *gpsbabel*
* Perl module *rodTools*.

### Examples

List all information about stations in a network.
```
$ ./net2all MVO-now
```
List all locations for a single station.
```
$ ./sta2loc MBGH
```
List all 'y' locations for stations or for a network.
```
$ ./sta2locy MBGH MBFR MSS1
$ ./net2locy MVO-BB
```
Create .csv file for a network and create .kml file.
```
$ ./net2locy MVO-BB | ./loc2csv > MVO-BB.csv
$ gpsbabel -i unicsv -f MVO-BB.csv -o kml -F MVO-BB.kml
$ cat MVO-BB.kml | ./kmltidy > MVO-BBa.kml
```
Create a .kml file for two networks.
```
$ ./net2kml2 MVO-BB MVO-SP
```

## Directories

| Directory       | Contents |
| -------------| -------------------|
| *created*   | Files and figures created from the database.|
| *data*   | Station data in text files.|
| *source_files*   | Various files that I got data from.|

## data

| File       | Contents |
| -------------| -------------------|
| *channels.txt* | Seismic channels used for a station.|
| *declination.txt* | Magnetic declination at a station.|
| *digitisers.txt*   | Digitsers serial numbers.|
| *gains.txt*   | Seismometer gains.|
| *locations.txt*   | Station locations.|
| *names.txt*   | Full names of stations.|
| *nets.txt*   | I can't remember what this is for.|
| *networks.txt*   | Groupings of stations to be extracted.|
| *notes.txt*   | Information that doesn't fit anywhere else.|
| *pseudonyms.txt*   | For stations with multiple codes.|
| *seismometers.txt*   | |
| *status.txt*   | Status of stations. Multiple entries allowed.|

* All other text files are non-essential.

### locations.txt

This file can contain more than one location for a station. The one that I trust is indicated witha 'Y' in the Primary column.

## scripts

| Script       | Function |
| -------------| -------------------|
| *gcf2loc*   | Calculates mean location from GPS *.gcf* files.|
| *kmltidy*   | Tidies up output of *gpsbabel*.|
| *loc2csv*   | Converts location information to the *gpsbabel* *unicsv* format.|
| *loc2csv2*   | Similar to *loc2csv* but adds the network.|
| *loc2hyp*   | Converts location information to a format suitable for *HYP*.|
| *net2all*   | Lists all information for all stations in a network.|
| *net2kml*   | Creates a .kml file for a network or networks.|
| *net2kml2*   |Creates a .kml file for a network or networks.|
| *net2loc*   | Lists locations for a network or networks.|
| *net2locy*   | Lists only the 'y' locations for a network or networks.|
| *net2sta*   | Lists stations for a network or networks.|
| *net2stalist*   | Lists station names for a network or networks.|
| *sac2sta*   | Lists stations for all SAC files in current directory.|
| *sta2loc*   | Lists all locations for stations.|
| *sta2locy*   | Lists only the 'y' locations for stations.|
| *stastatus*   | Lists station status.|

## Author

Roderick Stewart, Dormant Services Ltd

rod@dormant.org

https://services.dormant.org/

## Version History

* 1.0-dev
    * Working version

## License

This project is licensed to Montserrat Volcano Observatory in perpetuity.
