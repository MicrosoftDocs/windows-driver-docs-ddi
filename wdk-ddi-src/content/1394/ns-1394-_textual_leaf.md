---
UID: NS:1394._TEXTUAL_LEAF
title: _TEXTUAL_LEAF (1394.h)
description: The TEXTUAL_LEAF structure describes the device description that can be stored in the Configuration ROM of devices that satisfy the PC 98 or PC 99 specifications.
old-location: ieee\textual_leaf.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["TEXTUAL_LEAF structure"]
ms.keywords: "*PTEXTUAL_LEAF, 1394/PTEXTUAL_LEAF, 1394/TEXTUAL_LEAF, 1394stct_b63840e2-0a05-49e9-a533-9575f46af648.xml, IEEE.textual_leaf, PTEXTUAL_LEAF, PTEXTUAL_LEAF structure pointer [Buses], TEXTUAL_LEAF, TEXTUAL_LEAF structure [Buses], _TEXTUAL_LEAF"
req.header: 1394.h
req.include-header: 1394.h
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
targetos: Windows
req.typenames: TEXTUAL_LEAF, *PTEXTUAL_LEAF
f1_keywords:
 - _TEXTUAL_LEAF
 - 1394/_TEXTUAL_LEAF
 - PTEXTUAL_LEAF
 - 1394/PTEXTUAL_LEAF
 - TEXTUAL_LEAF
 - 1394/TEXTUAL_LEAF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _TEXTUAL_LEAF
 - PTEXTUAL_LEAF
 - TEXTUAL_LEAF
---

# _TEXTUAL_LEAF structure


## -description

The TEXTUAL_LEAF structure describes the device description that can be stored in the Configuration ROM of devices that satisfy the PC 98 or PC 99 specifications.

## -struct-fields

### -field TL_CRC

Specifies the CRC of the text string.

### -field TL_Length

Specifies the length of the text string, in bytes.

### -field TL_Spec_Id

Specifies which specification describes the meaning of the <b>TL_Language_ID</b> member.

### -field TL_Language_Id

Specifies the language of the <b>TL_Data</b> member.

### -field TL_Data

Specifies a vendor-specified textual description of the device.

## -see-also

<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_GET_CONFIGURATION_INFO</a>

