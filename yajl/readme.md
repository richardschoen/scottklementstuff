# YAJL - JSON Access from RPG
This is an IBM i port of YAJL, a very fast JSON parser/generator created by Lloyd Hilaiel of Mozilla fame.

You may also be interested in the handout (PDF of Powerpoint slides) for the talk I give on using YAJL from RPG. See PDF attached in this repo directory.

For instructions on how to install YAJL, please download the main YAJL file (YAJL.zip) and see the README.txt file inside the ZIP file.

Note: Updated March 27, 2014 to fix bugs with un-escaping of escaped strings, and pointer error in yajl_get_number.

Note: Updated April 4, 2014 to fix bug interpreting true/false values.

Note: Updated October 31, 2015 to enable support for escaping solidus and fix bug with yajl_tree_free.

Note: Updated February 24, 2017 to add yajl_stringify() routine.

Note: Updated March 31, 2017 to workaround problems in QtmhWrStout with large JSON buffers.

Note: Updated September 29, 2017 to add yajl_stringifyStr, yajl_copyBufStr and yajl_string_load_tree routines.

Note: Updated March 9, 2018 to add yajl_genFromNode routine.

Note: Updated April 17, 2018 to add support for RPG's DATA-INTO opcode.

Note: Updated May 17, 2018 added additional options to YAJLINTO.

Note: Updated Oct 1, 2018 added *STDIN support to YAJLINTO.

Note: Updated July 29, 2019 added YAJLGEN utility, and ability to write *STDIN data to IFS.

Note: Updated November 25, 2019 added YAJLDTAGEN (DATA-GEN interface), and yajl_addPreformattedPtr routine.

Note: Updated June 8, 2020 added new option "include empty arrays" to YAJLDTAGEN.

Note: Updated Oct 14, 2020 added yajl_clearBuf routine to clear generator buffer, and yajl_addNumF to help format numbers.

Note: Updated Jan 21, 2022 added YAJL_MEMORY_STATUS environment variable. Set it to an IFS path, and YAJLINTO will write a report showing how many objects are allocated in memory when YAJLINTO finishes parsing a document.

Note: Updated July 16, 2022 added new option "skip_nulls" to YAJLINTO. If set to true, it will skip elements that are set to null (as if they are not in the JSON document.)

Note: Updated October 19, 2022 added new subprocedure YAJL_get_bignumber() to return numbers at packed(63:20). This addresses concerns that yajl_get_number() is limited to packed(30:9).

August 16, 2023 Eliminate problems with yajl_get_number/yajl_get_bignumber when number is in floating point notation.

September 9, 2023 YAJLINTO now copies document buffer into teraspace to eliminate 16mb limit.

September 18, 2023 YAJLINTO now detects numeric json elements in floating point notation and converts them to decimal notation to avoid limitations in DATA-INTO.

April 9, 2024 make yajl_get_number and yajl_get_bignumber operate independently of the user's locale when interpreting numbers in floating point notation. Also added YAJL_addPreformattedUTF8Ptr.

April 11, 2024 Added support for ISO 8601 timestamps in YAJLR4 via YAJL_addTimestamp and YAJL_get_timestamp. Also added some stuff for compatibility with MDREST4i's YAJL support.

May 2, 2024 Added support for adding new values to a tree node via the YAJL_object_insert and YAJL_array_add routines.

May 3, 2024 Added an addditional parameter to the YAJL_addXXXX procedures to allow you to set the value to NULL (easier than calling YAJL_addNull manually)

Jun 6, 2024 Fix regression of yajl_addnumf(*omit:val) since null support added in May

Sep 6, 2024 Clear cached element name for null elements when skip_null: true

Sep 30, 2024 Add routines YAJL_getPathComp, YAJL_urlDecode

## File list
- yajl.zip - YAJL for IBM i   
- yajlv6r1.zip - YAJL for IBM i - V6R1   
- WORKINGJSON.zip - Working With JSON in RPG Sample Code   
- STOCKQTY.zip - STOCKQTY Sample  
- CUSTDETAIL.ZIP - Sample code for the blog entry "RPG and YAJL as well as Data-Into News  
❗v7r2+ and DATA-INTO PTFs are required to use this with the DATA-INTO opcode.   
