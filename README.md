# ise_logstash_pipeline

The problem with Cisco ISE Remote Logs is that for one event you get several lines of syslog information. So to use this in elasticsearch it is necessary that the lines get concatenated before they are sent into elasitc. The pipeline in ise.conf aims to receive remote logs on UDP port 9003, concatenate lines with the same msg_id into one line and lastly parse key-value pairs from the remaining data.
The main goal was to get information for the logging categories "Failed Attempts" and "Passed Authentications". Other categories where not tested with this pipeline.
