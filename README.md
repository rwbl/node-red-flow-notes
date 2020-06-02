# node-red-flow-notes

## Objectives
* To create a server based web application, to quickly scribble or store notes from any device in the local network.
* The application should be simple with few input fields and buttons to add, update, delete and export notes.
* The notes to be stored in a text file in JSON format.
* The application to run on a Raspberry Pi.

## Solution
Node-RED selected as the development tool running on a Raspberry Pi.
Two flows are defined, one for mobile use (smartphone) and the other for larger screen, i.e. desktop or tablet.
The flow functionality is the same, except the definition of the form to manage the notes.
Functionality:
* Form with fields Subject (input), Content (textarea), ID (input readonly)
* Note selection list - mobile: dropdown, desktop: list
* Buttons to
	* Add the newly created note
	* Update the selected note
	* Delete the selected note
	* Copy the selected note to the clipboard
	* Export all notes to a text file (with extention .exp) located in the notes folder
	* Clear all notes
The notes are stored in a single text file in JSON format, located as default in the folder:
```
/home/pi/notes.json
```
Pi is the username used.
The JSON format, is an array with note objects. Each note has properties:
```
{"id":NN,"subject":"SUBJECT","content":"CONTENT"}
```

Instead installting on a Raspberry Pi any other hardware can be used.

Note: The application error handling is not fully covered.

## Hardware
* Raspberry Pi 3B+

## Software
* Raspian OS - Raspbian GNU/Linux 10 (buster)
* Node-RED v1.0.6, node-red-dashboard v2.22.1

## Flows
* notes-mobile.flow
* notes-desktop.flow

## Installation
Import the flows into Node-RED, either both or mobile / desktop only.
The Node-RED tabs created are Notes Mobile and/or Notes Desktop.
Depending username used, the path to the notes file has to be adjusted (node "Set Flow Context, Set flow.filename). Default is user "pi".

