# pdf-manager

Convert, append, split, and e-mail* PDF documents. This is a minimally-viable product.

* e-mailing on client machines will not work without supplying your own e-mail address credentials in a file you create in the same directory called <b>email_credentials.txt</b>.

# Installation Instructions

The below installation instructions are for Ubuntu Linux environments; the software should be runnable on any environment assuming you have the correct packages installed.

Before running the entry-point to the software ($ python3 gui-connector.py), ensure that you have the following packages installed on your Ubuntu machine ($ sudo apt install $PACKAGE):

  1) gobject-introspection
  2) libgtk3-dev
  2) pkgconf
  3) python3-cairo
  4) pip
  
When pip is installed, use it to install the following libraries:
  1) pdfrw
  2) openpyxl
  3) filetype
  4) PyGObject
  
Now, you should be able to invoke the graphical user interface successfully from the Bash Shell:
  $ python3 gui-connector.py
  
To quit the program, you can either enter CTRL-C on the command line or hit the 'X' button at the top right corner.

![image](https://user-images.githubusercontent.com/66497798/188294407-5104bf10-82df-4e5a-a982-ec1951d6eafa.png)

# Conversion

To convert a file, select a file and a new type, then give it a new name. Finally, hit the convert button. The software will create new files for all types except PDF - for a PDF document, said document must already exist and have fillable fields, then the software will fill it in. While this is a limitation of the current implementation, the software still has the ability to fill in large numbers of fillable PDF's quickly using the command-line interface (see below).

# Appending

Append two PDFs together and give it a new name. Then, hit the append button.

# Splitting

Split a multi-page fillable PDF at the specified page numbers. Select a file, then fill in the page numbers you want to split it at. This will output several files depending on how many page numbers you decided to split at named <original_file_name>_part_<X>.pdf where X is a number specifying the part of the split the file represents.

# E-mailing

E-mail a PDF to yourself directly from the GUI application. Type in your e-mail address as well as a file to send as an attachment, then hit the e-mail button. NOTE: To have this feature work, you must add a file named <b>email_credentials.txt</b>. The first line should contain an e-mail address (through the g-mail service) and the second line should contain the password to said e-mail. The software currently has no "external" server-based e-mail address which it operates.

# Command-Line Interface

Type $ python3 cli.py

This will present to you the command line options. They are the same options that the GUI presents. This interface can be used to write shell scripts to handle processing of large amounts of documents.
