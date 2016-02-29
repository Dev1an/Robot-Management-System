## Usage

### Requirements

- RethinkDB
- Meteor
- Python

###Database
Run RethinkDB
```sh
cd Database
rethinkdb
```

Create a table named "`devices`" in the "`test`" database

### Web server
Run Meteor
```sh
cd "Web application"
meteor
```

### Robot discovery service
```sh
cd "Robot communication/python"
python discoveryRethinkdb.py
```

### Robot simulator
```sh
cd "Robot simulation/python"
python line_controller.py
```

```sh
cd "Robot simulation/python"
python thermo_former.py
```

### GUI
Open a browser and navigate to localhost:3000
