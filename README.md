# Metadata Histogram
![Metadata Histogram/CGI](https://github.com/SotiriosVrachas/metadata-histogram/raw/master/cgi.jpg "Metadata Histogram/CGI")

ABS used: 51g

Printing time: ~4 Hr.

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

## License
Metadata Histogram by Sotirios Vrachas is licensed under a Creative Commons Attribution-ShareAlike 4.0 International License.
