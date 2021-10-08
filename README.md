# checkmaster
Server assessment tool of requirements like open ports, available commands and stuffs


## Configuration file

json file like

````
{
    'ingoing_ports': [
        {'kind': 'tcp', 'port': 22, "location": "0.0.0.0"},
        {'kind': 'tcp', 'port': 8080, "location": "0.0.0.0"},
        {'kind': 'tcp', 'port': 8443, "location": "0.0.0.0"},
        {'kind': 'tcp', 'port': 80, status='CLOSED'},

        # ...
        {'kind': 'tcp', 'port': 5044, "location": "0.0.0.0"},
        {'kind': 'udp', 'port': 1514},
        {'kind': 'tcp', 'port': 1515, "location": "0.0.0.0"},


    ],
    'outgoing_ports': [
        {'addr': "that-host.net", "port":5150, "kind": "tcp"},
        {'addr': "that-host.net", "port":443, "kind": "tcp"},
        {'addr': "that-host.net", "port":5986, "kind": "tcp"}
        {'addr': "that-host.net", "port":22, "kind": "tcp"}
    ],

    "system_commands": [
        {"cmd": 'ping -c 1 google.com', "exit_status":0, stdout_regexp: "1 received", stderr_regexp: ""}
    ],

    "cpu": {'core_min': 8},
    "ram": {"free_min": "7GB"},

    "filesystems": [
        {"path":"/", "free_min":100000},
    ],

    "paths": [
        {"kind": 'file', "path":"./README.md", "status"="present"},
        {"kind": 'file', "path":"README.txt", "status"="absent"},
        {"kind": 'directory', "path":"READMEs", "status"="absent"},
    ],
}
````
