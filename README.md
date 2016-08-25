# AddressBook (Level 2)
* This is a CLI (Command Line Interface) Address Book application **written in OOP fashion**. 
* It is a Java sample application intended for students learning Software Engineering while using Java as 
  the main programming language. 
* It provides a **reasonably well-written** code example that is **significantly bigger** than what students 
  usually write in data structure modules. 
  
**Table of Contents**
* [User Guide](#user-guide)
* [Developer Guide](doc/DeveloperGuide.md) (separate page)
* [Learning Outcomes](#learning-outcomes)
* [Contributors](#contributors)
* [Contact Us](#contact-us)

-----------------------------------------------------------------------------------------------------
# User Guide

This product is not meant for end-users and therefore there is no user-friendly installer. 
Please refer to the [Setting up](#setting-up) section to learn how to set up the project.

#### Starting the program

**Using Eclipse**

1. Find the project in the `Project Explorer` or `Package Explorer` (usually located at the left side)
2. Right click on the project
3. Click `Run As` > `Java Application`
4. The program now should run on the `Console` (usually located at the bottom side)
5. Now you can interact with the program through the `Console`

**Using Command Line**

1. 'Build' the project using Eclipse
2. Open the `Terminal`/`Command Prompt`
3. `cd` into the project's `bin` directory
4. Type `java seedu.addressbook.Main`, then <kbd>Enter</kbd> to execute
5. Now you can interact with the program through the CLI

#### Changes from level 1
What's different from AddressBook-Level1:
* Support for storing address (`a/`) and tags (`t/`)
* Support for marking a contact detail as 'private' (`pa/`) (`pe/`) (`pp/`) 
* View details of a person (`view` : shows non-private details), (`viewall` : shows all details)

### Viewing help : `help`
Format: `help`

> Help is also shown if you enter an incorrect command e.g. `abcd`
 
### Adding a person: `add`
Adds a person to the address book<br>
Format: `add NAME [p]p/PHONE_NUMBER [p]e/EMAIL [p]a/ADDRESS [t/TAG]...` 
 
> Words in `UPPER_CASE` are the parameters, items in `SQUARE_BRACKETS` are optional, 
> items with `...` after them can have multiple instances. Order of parameters are fixed. 
> 
> Put a `p` before the phone / email / address prefixes to mark it as `private`. `private` details can only
> be seen using the `viewall` command.
> 
> Persons can have any number of tags (including 0)

Examples: 
* `add John Doe p/98765432 e/johnd@gmail.com a/John street, block 123, #01-01`
* `add Betsy Crowe e/betsycrowe@gmail.com pp/1234567 pa/Newgate Prison t/criminal t/friend`

### Listing all persons : `list`
Shows a list of all persons in the address book.<br>
Format: `list`

### Finding all persons containing any keyword in their name: `find`
Finds persons whose names contain any of the given keywords.<br>
Format: `find KEYWORD [MORE_KEYWORDS]`

> The search is case sensitive, the order of the keywords does not matter, only the name is searched, 
and persons matching at least one keyword will be returned (i.e. `OR` search).

Examples: 
* `find John`<br>
  Returns `John Doe` but not `john`
* `find Betsy Tim John`<br>
  Returns Any person having names `Betsy`, `Tim`, or `John`

### Deleting a person : `delete`
Deletes the specified person from the address book. Irreversible.<br>
Format: `delete INDEX`

> Deletes the person at the specified `INDEX`. 
  The index refers to the index number shown in the most recent listing.

Examples: 
* `list`<br>
  `delete 2`<br>
  Deletes the 2nd person in the address book.
* `find Betsy`<br> 
  `delete 1`<br>
  Deletes the 1st person in the results of the `find` command.

### View non-private details of a person : `view`
Displays the non-private details of the specified person.<br>
Format: `view INDEX`

> Views the person at the specified `INDEX`. 
  The index refers to the index number shown in the most recent listing.

Examples: 
* `list`<br>
  `view 2`<br>
  Views the 2nd person in the address book.
* `find Betsy` <br> 
  `view 1`<br>
  Views the 1st person in the results of the `find` command.

### View all details of a person : `viewall`
Displays all details (including private details) of the specified person.<br>
Format: `viewall INDEX`

> Views all details of the person at the specified `INDEX`. 
  The index refers to the index number shown in the most recent listing.

Examples: 
* `list`<br>
  `viewall 2`<br>
  Views all details of the 2nd person in the address book.
* `find Betsy`<br> 
  `viewall 1`<br>
  Views all details of the 1st person in the results of the `find` command.

### Clearing all entries : `clear`
Clears all entries from the address book.<br>
Format: `clear`  

#### Exiting the program : `exit`
Exits the program.<br>
Format: `exit`  

#### Saving the data 
Address book data are saved in the hard disk automatically after any command that changes the data.<br>
There is no need to save manually.

#### Changing the save location
Address book data are saved in a file called `addressbook.txt` in the project root folder.
You can change the location by specifying the file path as a program argument.

Example: 
* `java seedu.addressbook.Main mydata.txt`

> The file name must end in `.txt` for it to be acceptable to the program.
>
> When running the program inside Eclipse, you can set command line parameters 
  before running the program.

-----------------------------------------------------------------------------------------------------
# Learning Outcomes
Here are the things you should be able to do after studying this code and completing the
corresponding exercises.

# Exercises

#### ABL2-E1: Extract more classes 
(extract Unit, Street, PostalCode)
             
#### ABL2-E2: Improve exception handling

#### ABL2-E3: Add an `Interface` 
Example of an Interface `ReadOnlyPerson`
Add another Interface `ReadOnlyTag` as follows.
{diagram}

#### ABL2-E4:  Add `abstract` method 
Example `Contact::getDisplayString()`


#### ABL2-E5:  Encapsulate a variable 
Apply to `Contact::isPrivate`

#### ABL2-E6:  Add some unit tests

#### ABL2-E7:  Add some unit tests using TDD


-----------------------------------------------------------------------------------------------------
# Contributors

* [Leow Yijin](http://github.com/yijinl) : Main developer for AddressBook-level2
* [Damith C. Rajapakse](http://www.comp.nus.edu.sg/~damithch) : Project Advisor

-----------------------------------------------------------------------------------------------------
# Contact Us

* **Bug reports, Suggestions** : Post in our [issue tracker](https://github.com/se-edu/addressbook-level2/issues)
  if you noticed bugs or have suggestions on how to improve.
* **Contributing** : We welcome pull requests. Follow the process described [here](https://github.com/oss-generic/process)