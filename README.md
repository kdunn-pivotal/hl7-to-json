# Streaming HL7 to JSON parser

This project shows how to convert HL7 electronic medical record data into JSON, for loading into a data warehouse like Pivotal Greenplum.


### Usage:

    $ cat ORU^R01_AUS_PROFILE.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less
    $ cat ORU^R01_AUS_PROFILE_RAD.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less
    $ cat ACK.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less
    $ cat ACK^R01.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less

