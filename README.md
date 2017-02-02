# Metadata Histogram
![Metadata Histogram/CGI](https://github.com/SotiriosVrachas/metadata-histogram/raw/master/cgi.jpg "Metadata Histogram/CGI")
A seven day laptop usage physical profile. What can the timestamps alone of the metadata that I generating simply by using a computer revile about me?

## Documentation
ABS used: 51g

Printing time: ~4 Hr.

Software Stack: Debian GNU/Linux, FreeCAD, LibreOffice Calc, Inkscape, Blender
(for CGI)

### How it was done

```
sudo zcat /var/log/syslog.7.gz | awk -F':' '{print $1}' >> log
sudo zcat /var/log/syslog.6.gz | awk -F':' '{print $1}' >> log
sudo zcat /var/log/syslog.5.gz | awk -F':' '{print $1}' >> log
sudo zcat /var/log/syslog.4.gz | awk -F':' '{print $1}' >> log
sudo zcat /var/log/syslog.3.gz | awk -F':' '{print $1}' >> log
sudo zcat /var/log/syslog.2.gz | awk -F':' '{print $1}' >> log
sudo awk -F':' '{print $1}' /var/log/syslog.1 >> log
sudo awk -F':' '{print $1}' /var/log/syslog >> log

uniq -c log > logfreq
```
Then logfreq > chart.ods > data formating > chart.svg > lines to closed paths > waves.svg > waves.fcstd > extrude paths > wave*.stl

## Wanted features
Day 1 and 2 are missing the activity that hapend around 23:00 due to shorter
dataranges in calc.

Shorter process.

Commands for other log types. Git and Thunderbird store similar metadata
but for a longer period of time.

## License
Metadata Histogram by Sotirios Vrachas is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License.

## Inspiration
"I search, therefore I am" Workshop by Kyriaki Goni
