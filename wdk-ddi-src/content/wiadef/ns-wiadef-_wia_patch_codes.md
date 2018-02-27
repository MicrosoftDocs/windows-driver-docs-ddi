---
UID: NS:wiadef._WIA_PATCH_CODES
title: "_WIA_PATCH_CODES"
author: windows-driver-content
description: The WIA_PATCH_CODES structure stores header information for the patch code metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_patch_codes.htm
old-project: image
ms.assetid: CFD2403B-DDD4-4318-9084-1B3E3462FBDC
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: WIA_PATCH_CODES, WIA_PATCH_CODES structure [Imaging Devices], _WIA_PATCH_CODES, image.wia_patch_codes, wiadef/WIA_PATCH_CODES
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
-	wiadef.h
apiname:
-	WIA_PATCH_CODES
product: Windows
targetos: Windows
req.typenames: WIA_PATCH_CODES
req.product: Windows 10 or later.
---

# _WIA_PATCH_CODES structure


## -description


The <b>WIA_PATCH_CODES</b> structure stores header information for the patch code metadata report of one scan job (one call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543956">IWiaMiniDrv::drvAcquireItemData</a>).


## -syntax


````
typedef struct _WIA_PATCH_CODES {
  DWORD                Tag;
  DWORD                Version;
  DWORD                Size;
  DWORD                Count;
  WIA_PATCH_CODES_INFO PatchCodes[1];
} WIA_PATCH_CODES;
````


## -struct-fields




### -field Tag

Must be the literal 'WBAT', 4 single byte ASCII characters. 


### -field Version

Must be the value 0x00010000 (Version 1.0).


### -field Size

The complete size of this <b>WIA_PATCH_CODES</b> header structure, in bytes, including the complete size of the <a href="..\wiadef\ns-wiadef-_wia_patch_code_info.md">WIA_PATCH_CODES_INFO</a> list.


### -field Count

Specifies the number of <a href="..\wiadef\ns-wiadef-_wia_patch_code_info.md">WIA_PATCH_CODES_INFO</a> elements in the PatchCodes sequence.


### -field PatchCodes

Placeholder for a sequence of <b>Count</b> contiguous <a href="..\wiadef\ns-wiadef-_wia_patch_code_info.md">WIA_PATCH_CODES_INFO</a> structures.


## -remarks



The header must be followed by a sequence of patch code information structures, one for each detected patch code, in the order the patch codes were found and decoded.



