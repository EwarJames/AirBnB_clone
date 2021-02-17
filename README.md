<h1 align="center">HolbertonBnB</h1>
<p align="center">
   <img src="https://davikani.s3.eu-west-3.amazonaws.com/images/holberton/holberton.png">
</p>
<p align="center">A clone of AirBnB website.</p>

### Table of contents.</br>
* Introduction
* Installation
* Usage
* AUTHORS

## Introduction

This project is a full clone of the AirBnB website. It is still in progress
and at this first stage the main console has been developed. This first step is
very important because what is built during this stage will be the basis of all
the other projects including but not limited to the following:

##### HTML/CSS templating.
##### database storage
##### API
##### front-end integration

## Installation


Clone the repository with the following command

    git clone https://github.com/kimengu-david/AirBnB_clone.git
    
After cloning the repository Navigate to the "AirBnB" repository

    cd AirBnB
    

## Usage

### Interactive mode
To enter the interactive mode execute the following command  "./console"

    ./console
    (hbnb)

### Non interactive mode

To use the non-interactive You must use the echo command and pipe a string to  (./console).

    echo "create BaseModel" | ./console
    (hbnb) ebe5d7db-fa0d-49d8-b66b-92c3b964ddbc
    (hbnb)

#### Console Commands

The following commands are supported:

#### create
* Usage: `create <class name>`

Creates a new instance of a given class. The class' ID is printed and
the instance is saved to the file `file.json`.

```
$ ./console.py
(hbnb) create BaseModel
119be863-6fe5-437e-a180-b9892e8746b8
(hbnb)
(hbnb) create BaseModel
(hbnb) quit
$ cat file.json ; echo ""
{"BaseModel.119be863-6fe5-437e-a180-b9892e8746b8": {"updated_at": "2019-02-17T2
1:30:42.215277", "created_at": "2019-02-17T21:30:42.215277", "__class__": "Base
Model", "id": "119be863-6fe5-437e-a180-b9892e8746b8"}, {'id': 'd80e0344-63eb-43
4a-b1e0-07783522124e', 'created_at': datetime.datetime(2017, 11, 10, 4, 41, 7, 
842160), 'updated_at': datetime.datetime(2017, 11, 10, 4, 41, 7, 842235), 'name
': 'BaseModel'}}
```

#### show
* Usage: `show <class> <id>` or `<class>.show(<id>)`

Prints the string representation of a class instance

```
$ ./console.py
(hbnb) create User
1527b643-e143-47b2-bc37-ad44152e0ff7
(hbnb)
(hbnb) show User 1527b643-e143-47b2-bc37-ad44152e0ff7
[User] (1527b643-e143-47b2-bc37-ad44152e0ff7) {'id': '1527b643-e143-47b2-bc37-ad44152e0ff7
', 'created_at': datetime.datetime(2019, 2, 17, 21, 34, 3, 635828), 
'updated_at': datetime.datetime(2019, 2, 17, 21, 34, 3, 635828)}
(hbnb)
(hbnb) User.show(1527b643-e143-47b2-bc37-ad44152e0ff7)
[User] (1e32232d-5a63-4d92-8092-ac3240b29f46) {'id': '1e32232d-5a63-4d92-8092-a
c3240b29f46', 'created_at': datetime.datetime(2019, 2, 17, 21, 34, 3, 635828), 
'updated_at': datetime.datetime(2019, 2, 17, 21, 34, 3, 635828)}
(hbnb)
```

#### destroy
* Usage: `destroy <class> <id>` or `<class>.destroy(<id>)`

Deletes a class instance based on a given id.

```
$ ./console.py
(hbnb) create User
d2d789cd-7427-4920-aaae-88cbcf8bffe2
(hbnb) create Place
1527b643-e143-47b2-bc37-ad44152e0ff7
(hbnb)
(hbnb) destroy Place 1527b643-e143-47b2-bc37-ad44152e0ff7
(hbnb) quit
$ cat file.json ; echo ""
{}
```

#### all
* Usage: `all` or `all <class>`

Prints the string representations of all instances of a given class. If no
class name is provided, the command prints all instances of every class.

```
$ ./console.py
(hbnb) create BaseModel
a1d10dea-8e26-474f-9787-96d76d23e3ed
(hbnb) create BaseModel
3ec3423e-03e9-4f5f-8113-4e74995ab5eb
(hbnb) create User
f32beb2e-e937-4dae-b6bb-446c0b5ccb80
(hbnb)
(hbnb) all BaseModel
["[BaseModel] (122a1d10dea-8e26-474f-9787-96d76d23e3ed) {'updated_at': datetime.da
tetime(2019, 2, 17, 21, 45, 5, 963516), 'created_at': datetime.datetime(2019, 2
, 17, 21, 45, 5, 963516), 'id': '450490fd-344e-47cf-8342-126244c2ba99'}", "[Bas
eModel] (3ec3423e-03e9-4f5f-8113-4e74995ab5eb) {'updated_at': datetime.datetime
(2021, 2, 17, 21, 43, 56, 899348), 'created_at': datetime.datetime(2019, 2, 17,
21, 43, 56, 899348), 'id': 'fce2124c-8537-489b-956e-22da455cbee8'}"]
(hbnb)
(hbnb) all User
["[User] (f32beb2e-e937-4dae-b6bb-446c0b5ccb80) {'updated_at': datetime.datetim
e(2019, 2, 17, 21, 44, 44, 428413), 'created_at': datetime.datetime(2019, 2, 17
, 21, 44, 44, 428413), 'id': 'f32beb2e-e937-4dae-b6bb-446c0b5ccb80'}"]
(hbnb)
(hbnb) all
["[User] (8f2d75c8-fb82-48e1-8ae5-2544c909a9fe) {'updated_at': datetime.datetim
e(2019, 2, 17, 21, 44, 44, 428413), 'created_at': datetime.datetime(2019, 2, 17
, 21, 44, 44, 428413), 'id': '8f2d75c8-fb82-48e1-8ae5-2544c909a9fe'}", "[BaseMo
del] (450490fd-344e-47cf-8342-126244c2ba99) {'updated_at': datetime.datetime(20
19, 2, 17, 21, 45, 5, 963516), 'created_at': datetime.datetime(2019, 2, 17, 21,
45, 5, 963516), 'id': '450490fd-344e-47cf-8342-126244c2ba99'}", "[User] (b742db
c3-f4bf-425e-b1d4-165f52c6ff81) {'updated_at': datetime.datetime(2019, 2, 17, 2
1, 44, 15, 974608), 'created_at': datetime.datetime(2019, 2, 17, 21, 44, 15, 97
4608), 'id': 'b742dbc3-f4bf-425e-b1d4-165f52c6ff81'}", "[BaseModel] (fce2124c-8
537-489b-956e-22da455cbee8) {'updated_at': datetime.datetime(2019, 2, 17, 21, 4
3, 56, 899348), 'created_at': datetime.datetime(2019, 2, 17, 21, 43, 56, 899348
), 'id': 'fce2124c-8537-489b-956e-22da455cbee8'}"]
(hbnb)
```
#### update
* Usage: `update <class> <id> <attribute name> "<attribute value>"`

Updates a class instance based on a given id with a given key/value attribute
pair or dictionary of attribute pairs. If `update` is called with a single
key/value attribute pair, only "simple" attributes can be updated (ie. not
`id`, `created_at`, and `updated_at`).

```
$ ./console.py
(hbnb) create User
6f348019-0499-420f-8eec-ef0fdc863c02
(hbnb)
(hbnb) update User 6f348019-0499-420f-8eec-ef0fdc863c02 first_name "Holberton" 
(hbnb) show User 6f348019-0499-420f-8eec-ef0fdc863c02
[User] (6f348019-0499-420f-8eec-ef0fdc863c02) {'created_at': datetime.datetime(
2019, 2, 17, 21, 54, 39, 234382), 'first_name': 'Holberton', 'updated_at': date
time.datetime(2019, 2, 17, 21, 54, 39, 234382), 'id': '6f348019-0499-420f-8eec-
ef0fdc863c02'}
(hbnb)
```

## Authors :black_nib:
* **David Mutune Kimengu** <[kimengu-david](https://github.com/kimengu-david)>
* **Ewar James** <[EwarJames](https://github.com/EwarJames)>
