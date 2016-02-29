# Robot-Management-System
Realtime CMS for robots

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

### Robot simulator
```sh
cd "Robot simulation/python"
python line_controller.py
```

```sh
cd "Robot simulation/python"
python thermo_former.py
```
