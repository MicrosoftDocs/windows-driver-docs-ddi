---
UID: NS:wiadef._WIA_BARCODES
title: _WIA_BARCODES (wiadef.h)
description: The WIA_BARCODES structure stores header information for the barcode metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_barcodes.htm
tech.root: image
ms.assetid: 2B89FF49-4376-49A7-B7CC-1C67D89C7E7A
ms.date: 05/03/2018
keywords: ["_WIA_BARCODES structure"]
ms.keywords: WIA_BARCODES, WIA_BARCODES structure [Imaging Devices], _WIA_BARCODES, image.wia_barcodes, wiadef/WIA_BARCODES
f1_keywords:
 - "wiadef/WIA_BARCODES"
req.header: wiadef.h
req.include-header: Wiadef.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiadef.h
api_name:
- WIA_BARCODES
product:
- Windows
targetos: Windows
req.typenames: WIA_BARCODES
---

# _WIA_BARCODES structure


## -description


The <b>WIA_BARCODES</b> structure stores header information for the barcode metadata report of one scan job (one call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata">IWiaMiniDrv::drvAcquireItemData</a>).


## -struct-fields




### -field Tag

Must be the literal 'WBAR', 4 single byte ASCII characters. 


### -field Version

Must be the value 0x00010000 (Version 1.0).


### -field Size

The complete size of this <b>WIA_BARCODES</b> header structure, in bytes, including the complete size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_barcode_info">WIA_BARCODE_INFO</a> list.


### -field Count

Specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_barcode_info">WIA_BARCODE_INFO</a> elements in the Barcodes sequence.


### -field Barcodes

Placeholder for  a sequence of <b>Count</b> contiguous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_barcode_info">WIA_BARCODE_INFO</a> structures.


## -remarks



The header must be followed by a sequence of barcode information structures, one for each decoded barcode, in the order the barcodes were found and decoded.



