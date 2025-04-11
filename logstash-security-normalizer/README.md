# logstashSecops
## Overview
This project demonstrates how to use **Logstash** to ingest, parse, and normalize raw security log data into a structured format. The goal is to convert unstructured logs into structured JSONlike output, suitable for use in SIEM platforms or security analytics tools.

The pipeline expects input via stdin, allowing logs to be entered manually and the output is via stdout in rubydebug format


## Logstash Configuration
 **Filter**:
   grok to extract fields from the message.
   mutate to convert severity codes and add a custom severity field.
   mutate to remove unused or irrelevant fields.
 **Output**: Standard output using the rubydebug codec.

### Extracted and Normalized Fields

 Time = Log timestamp
 Avhost = Hostname of the system generating the log
 Application = Application name (e.g., antivirus)
 Pid = Process ID
 Event_type = Alert or event description (e.g., "Virus Found")
 Machine_Name = Name of the affected computer
 Machine_ip = IP address of the affected computer
 Severity = Mapped severity value from the original severity code
