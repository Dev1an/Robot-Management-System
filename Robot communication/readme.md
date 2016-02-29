# Robot communication

To read the robot's zyre messages I made implementations in three different languages.

- Go
- Javascript
- <b>Python</b>

The most robust implementation for the moment is the pyhton implementation.

## Go
Altough Go is better suited for this kind of tasks, there is a [bug](https://github.com/zeromq/gyre/issues/39)
in the current [zyre implementation](https://github.com/zeromq/gyre) making the Go implementation, unusable for the moment.

## Javascript
The Javascript implementation would make this project less complex by decreasing the total number of used programming languages
wich might be an advantage for future developers on this project. But the javascript bindings for Zyre are still in development at
this time.
