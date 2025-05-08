./created
output from scripts etc
./data
station information in text files
./old
the old software etc
./source_files
lists, spreadsheets, etc from various sources

net2all
creates a report 
$ ./net2all MVO-D MVO-DX > MVO-D.txt

net2sta
creates list of stations, one per line for a network or group of networks
$ ./net2sta MVO TR

sta2loc
creates a list of locations for a station, or group of stations
$ ./sta2loc MBGH TRN

sta2locy
creates a list of 'y' locations for a station, or group of stations
$ ./sta2locy MBGH TRN

net2loc
creates a list of 'y' locations for a network or group of networks
$ ./net2loc MVO TR

net2locy
creates a list of 'y' locations for a network or group of networks
$ ./net2locy MVO TR

======= THIS WORKS !! ========
loc2csv
converts loc formt to csv for excel etc, use in pipe
Note that uses tab not , as seperator
$ ./net2locy MVO | ./loc2csv > MVO.csv

gpsbabel -i unicsv -f MVO.csv -o kml -F MVO.kml

cat GU2009.kml | ./kmltidy > GU2009a.kml
then manually change stations to network, if you want.

or
./net2kml GSN-IU
./net2kml2 TR VE (names them as networks)