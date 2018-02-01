---
UID: NE:winspool.BIDI_TYPE
title: BIDI_TYPE
author: windows-driver-content
description: The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.
old-location: print\bidi_type.htm
old-project: print
ms.assetid: ebb79ad6-91a1-4bdf-a6f6-7e04ed2358d9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.bidi_type, winspool/BIDI_BLOB, winspool/BIDI_NULL, winspool/BIDI_STRING, BIDI_BOOL, BIDI_TYPE, BIDI_ENUM, BIDI_FLOAT, winspool/BIDI_ENUM, BIDI_STRING, BIDI_BLOB, BIDI_TEXT, winspool/BIDI_TYPE, winspool/BIDI_FLOAT, spoolfnc_35a684ef-3bbf-4f33-86e9-b4a3bddbbb51.xml, winspool/BIDI_INT, winspool/BIDI_TEXT, winspool/BIDI_BOOL, BIDI_NULL, BIDI_INT, BIDI_TYPE enumeration [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration is available in Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winspool.h
apiname:
-	BIDI_TYPE
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# BIDI_TYPE enumeration


## -description


The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.


## -syntax


````
typedef enum  { 
  BIDI_NULL    = 0,
  BIDI_INT     = 1,
  BIDI_FLOAT   = 2,
  BIDI_BOOL    = 3,
  BIDI_STRING  = 4,
  BIDI_TEXT    = 5,
  BIDI_ENUM    = 6,
  BIDI_BLOB    = 7
} BIDI_TYPE;
````


## -enum-fields




### -field BIDI_NULL

Indicates that there is no data.


### -field BIDI_INT

Indicates that the bidi data is an integer.


### -field BIDI_FLOAT

Indicates that the bidi data is a floating-point number.


### -field BIDI_BOOL

Indicates that the bidi data is either <b>TRUE</b> or <b>FALSE</b>.


### -field BIDI_STRING

Indicates that the bidi data is a Unicode character string.


### -field BIDI_TEXT

Indicates that the bidi data is a nonlocalizable Unicode string.


### -field BIDI_ENUM

Indicates that the bidi data value is a Unicode string.


### -field BIDI_BLOB

Indicates that the bidi data is binary data.


## -remarks


The following correspondence applies between Simple Network Management Protocol (SNMP) types and bidi types defined in the BIDI_TYPE enumeration.
<table>
<tr>
<th>SNMP type</th>
<th>Bidi type</th>
</tr>
<tr>
<td>
SNMP_SYNTAX_CNTR32

SNMP_SYNTAX_GAUGE32

SNMP_SYNTAX_INT

SNMP_SYNTAX_TIMETICKS

SNMP_SYNTAX_UINT32

</td>
<td>
BIDI_BOOL

BIDI_INT

</td>
</tr>
<tr>
<td>
SNMP_SYNTAX_IPADDR

SNMP_SYNTAX_OCTETS

SNMP_SYNTAX_OID

</td>
<td>
BIDI_ENUM

BIDI_STRING

BIDI_TEXT

</td>
</tr>
<tr>
<td>
SNMP_SYNTAX_CNTR64

SNMP_SYNTAX_OCTETS

SNMP_SYNTAX_OPAQUE

</td>
<td>
BIDI_BLOB

</td>
</tr>
<tr>
<td>
(none)

</td>
<td>
BIDI_FLOAT

</td>
</tr>
</table> 

See the smiValue structure in the Microsoft Windows SDK documentation for descriptions of the WinSNMP data types.


