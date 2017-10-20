# Streaming HL7 to JSON parser

This project shows how to convert HL7 electronic medical record data into JSON, for loading into a data warehouse like Pivotal Greenplum.


### Usage:

    $ cat ORU^R01_AUS_PROFILE.hl7 | PYTHONIOENCODING="ISO-8859-1" python hl7_to_dict.py | less
    $ cat ORU^R01_AUS_PROFILE_RAD.hl7 | PYTHONIOENCODING="ISO-8859-1"  python hl7_to_dict.py | less
    $ cat ACK.hl7 | PYTHONIOENCODING="ISO-8859-1"  python hl7_to_dict.py | less
    $ cat ACK^R01.hl7 | PYTHONIOENCODING="ISO-8859-1"  python hl7_to_dict.py | less


### Sample output:

running: `cat ACK^R01.hl7 | PYTHONIOENCODING="ISO-8859-1" python hl7_to_dict.py`

    MSH|^~\&|MO|SSSC3261|GE - Lab Systems|QML^2184^AUSNATA|200004120817+1000||ACK^R01|SSSC3261_20000412-7|P|2.3.1^AUS&Australia&ISO3166-1|||NE|NE|AUS|ASCII|en^english^ISO639
    MSA|AA|GELS_20000412-2.243
    {'msa': {'acknowledgement_code': {'id': {'id': 'AA'}},
             'message_control_id': {'st': {'st': 'GELS_20000412-2.243'}}},
     'msh': {'accept_acknowledgment_type': {'id': {'id': 'NE'}},
             'application_acknowledgment_type': {'id': {'id': 'NE'}},
             'character_set': {'id': {'id': 'ASCII'}},
             'country_code': {'id': {'id': 'AUS'}},
             'date_time_of_message': {'time_of_an_event': {'st': '200004120817+1000'}},
             'encoding_characters': {'st': {'st': '\\S\\\\R\\\\E\\\\T\\'}},
             'field_separator': {'st': {'st': '\\F\\'}},
             'message_control_id': {'st': {'st': 'SSSC3261_20000412-7'}},
             'message_type': {'message_type': {'id': 'ACK'},
                              'trigger_event': {'id': 'R01'}},
             'principal_language_of_message': {'identifier': {'st': 'en'},
                                               'name_of_coding_system': {'st': 'ISO639'},
                                               'text': {'st': 'english'}},
             'processing_id': {'processing_id': {'id': 'P'}},
             'receiving_application': {'namespace_id': {'is': 'GE - Lab Systems'}},
             'receiving_facility': {'namespace_id': {'is': 'QML'},
                                    'universal_id': {'st': '2184'},
                                    'universal_id_type': {'id': 'AUSNATA'}},
             'sending_application': {'namespace_id': {'is': 'MO'}},
             'sending_facility': {'namespace_id': {'is': 'SSSC3261'}},
             'version_id': {'internationalization_code': {'identifier': 'AUS',
                                                          'name_of_coding_system': 'ISO3166-1',
                                                          'text': 'Australia'},
                            'version_id': {'id': '2.3.1'}}}}

    END OF RECORD

### Record Generator:

    $ cd hl7-record-generator
    $ mvn clean package
    $ java -cp target/hl7-record-generator-1.0-SNAPSHOT-shaded.jar io.pivotal.pde.Application 10 /tmp/hl7-messages


