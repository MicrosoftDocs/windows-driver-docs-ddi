---
UID: NE:winspool.BIDI_TYPE
title: BIDI_TYPE
author: windows-driver-content
description: The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.
old-location: print\bidi_type.htm
old-project: print
ms.assetid: ebb79ad6-91a1-4bdf-a6f6-7e04ed2358d9
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: BIDI_TYPE, BIDI_TYPE
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
req.alt-api: BIDI_TYPE
req.alt-loc: winspool.h
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

SNMP_SYNTAX_CNTR32

SNMP_SYNTAX_GAUGE32

SNMP_SYNTAX_INT

SNMP_SYNTAX_TIMETICKS

SNMP_SYNTAX_UINT32

BIDI_BOOL

BIDI_INT

SNMP_SYNTAX_IPADDR

SNMP_SYNTAX_OCTETS

SNMP_SYNTAX_OID

BIDI_ENUM

BIDI_STRING

BIDI_TEXT

SNMP_SYNTAX_CNTR64

SNMP_SYNTAX_OPAQUE

BIDI_BLOB

(none)

BIDI_FLOAT

See the smiValue structure in the Microsoft Windows SDK documentation for descriptions of the WinSNMP data types.</p>