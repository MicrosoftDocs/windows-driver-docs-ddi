---
UID: NE:printoem._EATTRIBUTE_DATATYPE
title: "_EATTRIBUTE_DATATYPE"
author: windows-driver-content
description: The EATTRIBUTE_DATATYPE enumerates the possible data types for a global attribute, feature attribute or option attribute.
old-location: print\eattribute_datatype.htm
old-project: print
ms.assetid: 51d3e768-11b1-411d-89b1-4fec19306b97
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, A, B, D, E, EATTRIBUTE_DATATYPE, EATTRIBUTE_DATATYPE enumeration [Print Devices], I, P, R, T, U, Y, _, _EATTRIBUTE_DATATYPE, kADT_ASCII, kADT_BINARY, kADT_BOOL, kADT_CUSTOMSIZEPARAMS, kADT_DWORD, kADT_INT, kADT_LONG, kADT_RECT, kADT_SIZE, kADT_UNICODE, kADT_UNKNOWN, print.eattribute_datatype, print_unidrv-pscript_allplugins_6cda9036-f339-4700-808e-06c8867e5ba0.xml, printoem/EATTRIBUTE_DATATYPE, printoem/kADT_ASCII, printoem/kADT_BINARY, printoem/kADT_BOOL, printoem/kADT_CUSTOMSIZEPARAMS, printoem/kADT_DWORD, printoem/kADT_INT, printoem/kADT_LONG, printoem/kADT_RECT, printoem/kADT_SIZE, printoem/kADT_UNICODE, printoem/kADT_UNKNOWN"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	printoem.h
apiname:
-	EATTRIBUTE_DATATYPE
product: Windows
targetos: Windows
req.typenames: EATTRIBUTE_DATATYPE
req.product: Windows 10 or later.
---

# _EATTRIBUTE_DATATYPE enumeration


## -description


The EATTRIBUTE_DATATYPE enumerates the possible data types for a global attribute, feature attribute or option attribute.


## -syntax


````
typedef enum _EATTRIBUTE_DATATYPE { 
  kADT_UNKNOWN           = 0,
  kADT_BOOL              = 1,
  kADT_INT               = 2,
  kADT_LONG              = 3,
  kADT_DWORD             = 4,
  kADT_ASCII             = 5,
  kADT_UNICODE           = 6,
  kADT_BINARY            = 7,
  kADT_SIZE              = 8,
  kADT_RECT              = 9,
  kADT_CUSTOMSIZEPARAMS  = 10
} EATTRIBUTE_DATATYPE;
````


## -enum-fields




### -field kADT_UNKNOWN

The attribute is of unknown type.


### -field kADT_BOOL

The attribute is of type BOOL.


### -field kADT_INT

The attribute is of type INT.


### -field kADT_LONG

The attribute is of type LONG.


### -field kADT_DWORD

The attribute is of type DWORD.


### -field kADT_ASCII

The attribute is an ASCII string. 


### -field kADT_UNICODE

The attribute is a Unicode string.


### -field kADT_BINARY

The attribute consists of binary data.


### -field kADT_SIZE

The attribute is of type SIZE.


### -field kADT_RECT

The attribute is of type RECT.


### -field kADT_CUSTOMSIZEPARAMS

The attribute is an array containing CUSTOMPARAM_MAX (a constant defined in printoem.h) elements. Each element is a <a href="..\printoem\ns-printoem-_customsizeparam.md">CUSTOMSIZEPARAM</a> structure.


## -see-also

<a href="..\printoem\ns-printoem-_customsizeparam.md">CUSTOMSIZEPARAM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20EATTRIBUTE_DATATYPE enumeration%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

