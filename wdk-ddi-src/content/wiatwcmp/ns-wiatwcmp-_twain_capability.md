---
UID: NS:wiatwcmp._TWAIN_CAPABILITY
title: _TWAIN_CAPABILITY (wiatwcmp.h)
description: The TWAIN_CAPABILITY structure holds information used when a TWAIN-compatible application communicates with a WIA driver.
old-location: image\twain_capability.htm
tech.root: image
ms.assetid: 79a2155d-eb06-4095-9fe6-b95d93e46211
ms.date: 05/03/2018
keywords: ["_TWAIN_CAPABILITY structure"]
ms.keywords: "*PTWAIN_CAPABILITY, PTWAIN_CAPABILITY, PTWAIN_CAPABILITY structure pointer [Imaging Devices], TWAIN_CAPABILITY, TWAIN_CAPABILITY structure [Imaging Devices], _TWAIN_CAPABILITY, image.twain_capability, wiastrct_12204cb8-d0ad-46d5-a741-4522ba28006b.xml, wiatwcmp/PTWAIN_CAPABILITY, wiatwcmp/TWAIN_CAPABILITY"
f1_keywords:
 - "wiatwcmp/TWAIN_CAPABILITY"
req.header: wiatwcmp.h
req.include-header: Wiatwcmp.h
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
- wiatwcmp.h
api_name:
- TWAIN_CAPABILITY
product:
- Windows
targetos: Windows
req.typenames: TWAIN_CAPABILITY, *PTWAIN_CAPABILITY
---

# _TWAIN_CAPABILITY structure

## -description

The TWAIN_CAPABILITY structure holds information used when a TWAIN-compatible application communicates with a WIA driver.

## -struct-fields

### -field lSize

Specifies the size, in bytes, of the TWAIN_CAPABILITY structure.

### -field lMSG

Specifies the particular TWAIN message, which can be one of the following values:

| Value | Meaning |
| --- | --- |
| MSG_GET | Get a capability. |
| MSG_GETCURRENT | Get the current capability. |
| MSG_GETDEFAULT | Get the default capability. |
| MSG_RESET | Reset the capability. |
| MSG_SET | Set a capability. |

### -field lCapID

Specifies the ID of the capability to set or get.

### -field lConType

Specifies the capability's container type.

### -field lRC

Specifies the TWAIN return code. This value can be on of the following:

| Value | Meaning |
| --- | --- |
| TWRC_FAILURE | The capability specified by the **lCapID** member is not supported. |
| TWRC_SUCCESS | The capability specified by the **lCapID** member is supported. |
| TWRC_SUCCESS | See the **Remarks** section. |

### -field lCC

Specifies the TWAIN condition code. This value can be one of the following:

| Value | Meaning |
| --- | --- |
| TWCC_BUMMER | The operation failed for an unknown reason. |
| TWCC_SUCCESS | The operation was successful. |
| TWCC_XXX | See the **Remarks** section. |

### -field lDataSize

Specifies the size, in bytes of the data in the **Data** array.

### -field Data

Is an array that contains the capability data. The actual size, in bytes, of the array is indicated by the **lDataSize** member.

## -remarks

A TWAIN-capable application communicates with a WIA driver by way of the TWAIN compatibility later to find out whether the driver has any private capabilities, and if so, what they are. A TWAIN_CAPABILITY structure is used in this communication. For more information, see [TWAIN Compatibility](https://docs.microsoft.com/windows-hardware/drivers/image/twain-compatibility).

The TWAIN return codes and control codes are defined in *twain.h*, which can be obtained from the [TWAIN Working Group](https://www.twain.org).
