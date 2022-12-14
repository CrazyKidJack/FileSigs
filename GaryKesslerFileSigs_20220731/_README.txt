_README.txt (04/27/2022)

In addition to this README file, the ZIP package includes eight data files:

  o  customsigs_GCK.txt
  o  file_sigs_RAW.txt
  o  file_sigs.json
  o  FTK_sigs_GCK.zip
  o  scalpel_GCK.conf
  o  signatures_GCK.txt
  o  TrID_sigs_GCK.zip

Other files in this package include:

  o  _README.txt
  o  GKA_software_license.pdf


***** NOTE that additional information about the file types might *****
***** be present in http://www.garykessler.net/file_sigs.html     *****

***** customsigs_GCK.txt *****

customsigs_GCK.txt is the set of file signatures is a format that can be used by Tim Coakley's Simple Carver Lite (SCL) software (http://www.simplecarver.com/tool.php?toolname=Simple%20Carver%20Lite). Each record in the file has three, comma-separated fields:

  FileDescription,FileSignature,Extensions

An example entry would be:

  JPEG2000 image files,00 00 00 0C 6A 50 20 20,JP2

To use customsigs_GCK.txt, copy the file to the directory where Simple Carver Lite is installed and rename it to customsigs.txt.

***** file_sigs_RAW.txt *****

file_sigs_RAW.txt is the set of all file signatures in a comma-delimited text file. Each file has six fields:

   Description,Header (hex),Extension,FileClass,Header_offset,Trailer (hex)

As an example, a JPEG file entry looks like:

   JPEG/EXIF/SPIFF images,FF D8 FF,JFIF/JPE/JPEG/JPG,Picture,0,FF D9


***** file_sigs.json *****

file_sigs,json is the set of all file signatures in a JavaScript Object Notation (JSON) text file. Each file signature is defined in its own field. As an example, consider the following signature:

   JPEG/EXIF/SPIFF images,FF D8 FF,JFIF/JPE/JPEG/JPG,Picture,0,FF D9

A JSON file with a single entry for the signature above might look like:

{
  "name": "GCK's File Signature Table",
  "program version": "4.4",
  "file signature date": "04/27/2022",
  "filesigs":
    [
      {
      "File description": "JPEG/EXIF/SPIFF images"
      "Header (hex)": "FF D8 FF"
      "File extension": "JFIF/JPE/JPEG/JPG"
      "FileClass": "Picture"
      "Header offset": "0"
      "Trailer (hex)": "FF D9"
      },
    ]
}


***** FTK_sigs_GCK.zip *****

FTK_sigs_GCK.zip is a ZIP file containing a directory called FTK_sigs_GCK, which contains two files for every defined signature. These files may be used with AccessData's Forensic Toolkit (FTK).

Each file signature is defined in a text file and an XML file. A text file contains a file description, extension, signature, and offset (number of bytes from where the signature starts from the beginning of the file). An example file, "JPEG2000 image files JP2.txt", is shown below:

  File Description: JPEG2000 image files

  File Extension: JP2

  Offset: 0

  Signature: 00-00-00-0C-6A-50-20-20


An XML file contains a file description, extension, signature, number of bytes in the signature, and offset, plus some other fields. An example file, "JPEG2000 image files JP2.xml", is shown below:

  <?xml version="1.0" encoding="UTF-8"?>
  <CUSTOMCARVER><DATACARVER
  version="0.0.0.0"><ID>77001</ID><TYPE>2</TYPE><NAME>JPEG2000 image
  files/NAME><EXT><EXT_ID>0</EXT_ID><EXT_NAME>JP2</EXT_NAME></EXT><MAIN_SIG>
  <OFFSET>0</OFFSET><NUM_BYTES>8</NUM_BYTES><SIG>0000000C6A502020</SIG>
  </MAIN_SIG><AUTHOR>Gary C. Kessler</AUTHOR><DESCRIPTION>JPEG2000 image 
  files</DESCRIPTION></DATACARVER><FTYPE>1003</FTYPE><MAX_SIZE>10000000000000
  </MAX_SIZE><MIN_SIZE>0</MIN_SIZE></CUSTOMCARVER>

To install a specific Custom Carver file for use in FTK, download the files to your computer. In the FTK Case Manager, select Manage, Carvers. In the Manage Shared Custom Carvers dialogue box, click Import. Note that each carver must be imported individually. More information -- and carving files -- can be found at https://support.accessdata.com/hc/en-us/articles/203423159-Custom-Carvers.


***** scalpel_GCK.conf *****

scalpel_GCK.conf is a set of file signatures that can be used with Scalpel (and compatible with Foremost 0.69).

[[NOTE: This format is supported for historical purposes only, as it appears that Scalpel is no longer actively maintained.]]

Since this version of scalpel_GCK.conf is generated by a script, it does not contain all of the detail that the standard scalpel.conf has. Nevertheless, it has the basic components:

  FileExtension<tab>CaseSensitive<tab>FileSize<tab>Header<tab>Trailer

Note that the "?" in the header or trailer field is used as a wildcard.

By way of example, a JPEG file is listed as:

  JPG<tab>y<tab>2500000<tab>\xff\xd8\xff\xe0\x00\x10<tab>\xff\xd9

More information about Scalpel, including a copy of the standard scalpel.conf file, can be found at https://github.com/sleuthkit/scalpel.


***** signatures_GCK.txt *****

signatures_GCK.txt is the set of file signatures is a format that can be used by Tim Coakley's Simple Carver (SC) Suite (http://www.simplecarver.com/index.php). Each record in the file has six, comma-separated fields:

  FileDescription,FileSignature,Extensions,"Hex","N/A",Category

An example entry would be:

  JPEG2000 image files,00 00 00 0C 6A 50 20 20,Hex,N/A,JP2,Picture

To use signatures_GCK.txt, copy the file to the directory where Simple Carver is installed and rename it to signatures.txt.


***** TrID_sigs_GCK.zip *****

TrID_sigs_GCK.zip is a ZIP file containing a directory called TrID_sigs_GCK. This directory contains one file for every defined signature, that can be used with Marco Pontello's <a href="https://mark0.net/soft-trid-e.html" target="_blank"> TrID - File Identifier</a> utility.  (Marco has a set of files that also works with his utility but I was asked to create this so...).

Each file signature is defined is an XML file that contains a file description, extension, signature, offset, and a bunch of other information. An example file, "JPEG2000 image files JP2.trid.xml", is shown below:

<TrID ver="2.00">
  <Info>
    <FileType>JPEG2000 image files</FileType>
    <Ext>JP2</Ext>
    <User>Gary C. Kessler</User>
    <E-Mail>gck@garykessler.net</E-Mail>
    <Home>http://www.garykessler.net</Home>
  </Info>
  <General>
    <FileNum>1</FileNum>
    <Refine>Gary C. Kessler</Refine>
    <Date>
      <Year>2014</Year>
      <Month>5</Month>
      <Day>16</Day>
    </Date>
    <Time>
      <Hour>18</Hour>
      <Min>40</Min>
      <Sec>31</Sec>
    </Time>
    <Creator>GCK's convert_sigs v4.3</Creator>
  </General>
  <FrontBlock>
    <Pattern>
      <Bytes>0000000C6A502020</Bytes>
      <Pos>0</Pos>
    </Pattern>
  </FrontBlock>
</TrID>


***** Errors, issues, comments... *****

If there are any problems, comments, corrections, additions, or suggestions, please contact Gary Kessler at gck@garykessler.net.

