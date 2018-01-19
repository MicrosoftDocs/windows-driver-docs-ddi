---
UID: NS:wiadef._WIA_BARCODES
title: _WIA_BARCODES
author: windows-driver-content
description: The WIA_BARCODES structure stores header information for the barcode metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_barcodes.htm
old-project: image
ms.assetid: 2B89FF49-4376-49A7-B7CC-1C67D89C7E7A
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _WIA_BARCODES, WIA_BARCODES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiadef.h
req.include-header: Wiadef.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIA_BARCODES
req.alt-loc: wiadef.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.typenames: WIA_BARCODES
req.product: Windows 10 or later.
---

# _WIA_BARCODES structure



## -description
The <b>WIA_BARCODES</b> structure stores header information for the barcode metadata report of one scan job (one call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543956">IWiaMiniDrv::drvAcquireItemData</a>).



## -syntax

````
typedef struct _WIA_BARCODES {
  DWORD            Tag;
  DWORD            Version;
  DWORD            Size;
  DWORD            Count;
  WIA_BARCODE_INFO Barcodes[1];
} WIA_BARCODES;
````


## -struct-fields

### -field Tag

Must be the literal 'WBAR', 4 single byte ASCII characters. 


### -field Version

Must be the value 0x00010000 (Version 1.0).


### -field Size

The complete size of this <b>WIA_BARCODES</b> header structure, in bytes, including the complete size of the <a href="..\wiadef\ns-wiadef-_wia_barcode_info.md">WIA_BARCODE_INFO</a> list.


### -field Count

Specifies the number of <a href="..\wiadef\ns-wiadef-_wia_barcode_info.md">WIA_BARCODE_INFO</a> elements in the Barcodes sequence.


### -field Barcodes

Placeholder for  a sequence of <b>Count</b> contiguous <a href="..\wiadef\ns-wiadef-_wia_barcode_info.md">WIA_BARCODE_INFO</a> structures.


## -remarks
The header must be followed by a sequence of barcode information structures, one for each decoded barcode, in the order the barcodes were found and decoded.</p>