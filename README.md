# gvm-tools-example

## Install gvm-tools:

sudo python3 -m pip install gvm-tools

## Create Target:

- sudo gvm-cli --gmp-username username --gmp-password password socket --xml "<create_target><name>test2</name><hosts>127.0.0.1</hosts><port_list id='33d0cd82-57c6-11e1-8ed1-406186ea4fc5'/><alive_tests>Consider Alive</alive_tests></create_target>"

## Create Task:

- sudo gvm-cli --gmp-username username --gmp-password password socket --xml '<create_task><name>Scan Webserver</name><comment>Hourly scan f the webserver</comment><config id="daba56c8-73ec-11df-a475-002264764cea"/><target id="e9b80895-ac11-4215-99cd-a02d1ae508b9"/><preferences><preference><scanner_namemax_checks</scanner_name><value>2</value></preference><preference><scanner_name>max_hosts</scanner_name><value>10</value></preference></preferences></create_task>'

## Start Task:

- sudo gvm-cli --gmp-username username --gmp-password password socket --xml '<start_task task_id="f3fbe815-160e-4c3b-aab3-7c61116d6910"/>'

## Tast Progress:

- sudo gvm-cli --gmp-username username --gmp-password password socket --xml '<get_tasks task_id="f3fbe815-160e-4c3b-aab3-7c61116d6910"/>' | grep progress

## TXT Report:

- sudo gvm-cli --gmp-username username --gmp-password password socket --xml '<get_reports report_id="09da1028-14dd-4d6b-9fe0-20c183d9a400" format_id="a3810a62-1f62-11e1-9219-406186ea4fc5" filter="apply_overrides=0 levels=hml rows=100 min_qod=70 first=1 sort-reverse=severity" details="1"/>'

- Base64 decode between </report_format> and </report>


## Resources:

- https://readthedocs.org/projects/gvm-tools/downloads/pdf/latest/
- https://docs.greenbone.net/GSM-Manual/gos-5/en/gmp.html
- https://docs.greenbone.net/API/GMP/gmp-8.0.html
