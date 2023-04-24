---
UID: NE:winspool.BIDI_TYPE
title: BIDI_TYPE (winspool.h)
description: The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.
tech.root: print
ms.date: 03/09/2023
keywords: ["BIDI_TYPE enumeration"]
ms.keywords: BIDI_BLOB, BIDI_BOOL, BIDI_ENUM, BIDI_FLOAT, BIDI_INT, BIDI_NULL, BIDI_STRING, BIDI_TEXT, BIDI_TYPE, BIDI_TYPE enumeration [Print Devices], print.bidi_type, spoolfnc_35a684ef-3bbf-4f33-86e9-b4a3bddbbb51.xml, winspool/BIDI_BLOB, winspool/BIDI_BOOL, winspool/BIDI_ENUM, winspool/BIDI_FLOAT, winspool/BIDI_INT, winspool/BIDI_NULL, winspool/BIDI_STRING, winspool/BIDI_TEXT, winspool/BIDI_TYPE
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
targetos: Windows
req.typenames: BIDI_TYPE
f1_keywords:
 - BIDI_TYPE
 - winspool/BIDI_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winspool.h
api_name:
 - BIDI_TYPE
---

## -description

The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation.

## -enum-fields

### -field BIDI_NULL

Indicates that there is no data.

### -field BIDI_INT

Indicates that the bidi data is an integer.

### -field BIDI_FLOAT

Indicates that the bidi data is a floating-point number.

### -field BIDI_BOOL

Indicates that the bidi data is either **TRUE** or **FALSE**.

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

| SNMP type | Bidi type |
|---|---|
| SNMP_SYNTAX_CNTR32, SNMP_SYNTAX_GAUGE32, SNMP_SYNTAX_INT, SNMP_SYNTAX_TIMETICKS, SNMP_SYNTAX_UINT32 | BIDI_BOO,L BIDI_INT |
| SNMP_SYNTAX_IPADDR, SNMP_SYNTAX_OCTETS, SNMP_SYNTAX_OID | BIDI_ENUM, BIDI_STRING, BIDI_TEXT |
| SNMP_SYNTAX_CNTR64, SNMP_SYNTAX_OCTETS, SNMP_SYNTAX_OPAQUE | BIDI_BLOB |
| (none) | BIDI_FLOAT |

See the smiValue structure in the Microsoft Windows SDK documentation for descriptions of the WinSNMP data types.
