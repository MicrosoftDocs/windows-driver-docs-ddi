---
UID: NS:ntnls._CPTABLEINFO
title: _CPTABLEINFO
author: windows-driver-content
description: Stores the NLS file formats.
old-location: kernel\cptableinfo.htm
old-project: kernel
ms.assetid: 20EE0017-760E-48A1-8658-2A0278843074
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PCPTABLEINFO, kernel.cptableinfo, ntnls/CPTABLEINFO, ntnls/PCPTABLEINFO, CPTABLEINFO, *PCPTABLEINFO, PCPTABLEINFO structure pointer [Kernel-Mode Driver Architecture], CPTABLEINFO structure [Kernel-Mode Driver Architecture], _CPTABLEINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntnls.h
req.include-header: 
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
-	Ntnls.h
apiname: 
-	CPTABLEINFO
product: Windows
targetos: Windows
req.typenames: CPTABLEINFO, *PCPTABLEINFO
---

# _CPTABLEINFO structure


## -description


Stores the NLS file formats.


## -syntax


````
typedef struct _CPTABLEINFO {
  USHORT  CodePage;
  USHORT  MaximumCharacterSize;
  USHORT  DefaultChar;
  USHORT  UniDefaultChar;
  USHORT  TransDefaultChar;
  USHORT  TransUniDefaultChar;
  USHORT  DBCSCodePage;
  UCHAR   LeadByte[MAXIMUM_LEADBYTES];
  PUSHORT MultiByteTable;
  PVOID   WideCharTable;
  PUSHORT DBCSRanges;
  PUSHORT DBCSOffsets;
} CPTABLEINFO, *PCPTABLEINFO;
````


## -struct-fields




### -field CodePage

Specifies the code page number.


### -field MaximumCharacterSize

Specifies the maximum length in bytes of a character.


### -field DefaultChar

Specifies the default character (MB).


### -field UniDefaultChar

Specifies the default character (Unicode).


### -field TransDefaultChar

Specifies the translation of the default character (Unicode).


### -field TransUniDefaultChar

Specifies the translation of the Unicode default character (MB).


### -field DBCSCodePage

Specifies non-zero for DBCS code pages.


### -field LeadByte

Specifies the lead byte ranges.


### -field MultiByteTable

Specifies a pointer to a MB translation table.


### -field WideCharTable

Specifies a pointer to a WC translation table.


### -field DBCSRanges

Specifies a pointer to DBCS ranges.


### -field DBCSOffsets

Specifies a pointer to DBCS offsets.

