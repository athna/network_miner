# Network Miner
Network Miner generates a network map by sending SNMP requests (LLDP/CDP/EDP).

![D3.js display](http://i.imgur.com/kFvCZty.png)

## Table of contents:
- [Installation](#installation)
- [How to use](#how-to-use)
- [Test files](#test-files)
- [Roadmap](#roadmap)

# Installation
Clone this repository :

`git clone https://github.com/tux-00/network_miner.git`

Download dependencies :

`cd network_miner`

`bower install`

Check [bower.io](http://bower.io/) website for more informations about Bower.

# How to use
* EDP/CDP need to be enabled on your SNMP devices.
* Edit [data_mining.php](data_mining.php) and set an hostname (or ip address) and the dig level at this line:  `recursive_search('eswctb08ma', 9);`
* Run index.php on your web browser.

# Test files
You can test Network Miner without the appropriate environment.

To test Network Miner, you need first to copy the content of a json example data file (located in [test/data/](test/data/)) to your *data* directory.

Once the file is copied you need to comment this line to avoid overwrite on *snmp_data.json*: 
```
file_put_contents('./data/snmp_data.json', json_encode(array('nodes' => $nodes, 
 'links' => $links)),
 LOCK_EX);
```

**JSON data faker**

If you want to submit data for testing purpose you can use the [json_data_faker.py](test/data/json_data_faker.py) Python 2.7 script to fake every device names in your JSON file.

To use this script you need to install *faker* module with `pip install fake-factory`.

# Roadmap
* Autorefresh map data
* Save maps as PDF, PNG ...
* Icinga plugin
