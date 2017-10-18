# Streaming HL7 to JSON parser

This project shows how to convert HL7 electronic medical record data into JSON, for loading into a data warehouse like Pivotal Greenplum.


### Usage:

    $ cat ORU^R01_AUS_PROFILE.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less
    $ cat ORU^R01_AUS_PROFILE_RAD.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less
    $ cat ACK.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less
    $ cat ACK^R01.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py | less


### Sample output:

running: `cat ACK^R01.hl7 | /Users/kdunn/anaconda3/bin/python hl7_to_dict.py`

    {'msh': {'accept_acknowledgment_type': {'id': {'id': 'NE'}},
         'alternate_character_set_handling_scheme': {'id': {'id': 'AA'}},
         'application_acknowledgment_type': {'id': {'id': 'NE'}},
         'character_set': {'id': {'id': 'ASCII'}},
         'country_code': {'id': {'id': 'AUS'}},
         'date_time_of_message': {'time_of_an_event': {'st': '200004120817+1000'}},
         'encoding_characters': {'st': {'st': '\\S\\\\R\\\\E\\\\T\\'}},
         'field_separator': {'st': {'st': '\\F\\'}},
         'message_control_id': {'st': {'st': 'SSSC3261_20000412-7'}},
         'message_type': {'message_type': {'id': 'ACK'},
                          'trigger_event': {'id': 'R01'}},
         'none': {'varies_1': {'st': 'GELS_20000412-2.243'}},
         'principal_language_of_message': {'identifier': {'st': 'en'},
                                           'name_of_coding_system': {'st': 'ISO639\n'
                                                                           'MSA'},
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


