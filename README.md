A realtime web application that allows users to

- View information about robots in the network. The information contains
  - It's current state
  - What it has done in the past
  - What it will do in the future
- Send information to the robots to update it's configuration

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

Create two tables in the "`test`" database

- `modules`
  - add a secondary index: `uuid`
- `events`
  - add secondary indices:
    - `sender_UUID`
    - `timestamp`
    - `type`

### Web server
Run Meteor
```sh
cd "Web application"
meteor
```

### Database mediator
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