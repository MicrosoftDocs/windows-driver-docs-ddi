---
UID: NE:printoem._EATTRIBUTE_DATATYPE
title: "_EATTRIBUTE_DATATYPE"
author: windows-driver-content
description: The EATTRIBUTE_DATATYPE enumerates the possible data types for a global attribute, feature attribute or option attribute.
old-location: print\eattribute_datatype.htm
old-project: print
ms.assetid: 51d3e768-11b1-411d-89b1-4fec19306b97
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: EATTRIBUTE_DATATYPE, EATTRIBUTE_DATATYPE enumeration [Print Devices], _EATTRIBUTE_DATATYPE, kADT_ASCII, kADT_BINARY, kADT_BOOL, kADT_CUSTOMSIZEPARAMS, kADT_DWORD, kADT_INT, kADT_LONG, kADT_RECT, kADT_SIZE, kADT_UNICODE, kADT_UNKNOWN, print.eattribute_datatype, print_unidrv-pscript_allplugins_6cda9036-f339-4700-808e-06c8867e5ba0.xml, printoem/EATTRIBUTE_DATATYPE, printoem/kADT_ASCII, printoem/kADT_BINARY, printoem/kADT_BOOL, printoem/kADT_CUSTOMSIZEPARAMS, printoem/kADT_DWORD, printoem/kADT_INT, printoem/kADT_LONG, printoem/kADT_RECT, printoem/kADT_SIZE, printoem/kADT_UNICODE, printoem/kADT_UNKNOWN
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	EATTRIBUTE_DATATYPE
product: Windows
targetos: Windows
req.typenames: EATTRIBUTE_DATATYPE
---

# _EATTRIBUTE_DATATYPE enumeration


## -description


The EATTRIBUTE_DATATYPE enumerates the possible data types for a global attribute, feature attribute or option attribute.


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

The attribute is an array containing CUSTOMPARAM_MAX (a constant defined in printoem.h) elements. Each element is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547337">CUSTOMSIZEPARAM</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547337">CUSTOMSIZEPARAM</a>
 

 

