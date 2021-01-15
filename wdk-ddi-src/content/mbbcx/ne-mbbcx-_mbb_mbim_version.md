---
UID: NE:mbbcx._MBB_MBIM_VERSION
title: _MBB_MBIM_VERSION (mbbcx.h)
description: The MBB_MBIM_VERSION enumeration defines the version of the MBIM specification that a client driver and its device support.
tech.root: netvista
ms.date: 09/27/2019
keywords: ["MBB_MBIM_VERSION enumeration"]
ms.keywords: _MBB_MBIM_VERSION, MBB_MBIM_VERSION,
req.header: mbbcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: MBB_MBIM_VERSION
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _MBB_MBIM_VERSION
 - mbbcx/_MBB_MBIM_VERSION
 - MBB_MBIM_VERSION
 - mbbcx/MBB_MBIM_VERSION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - mbbcx.h
api_name:
 - _MBB_MBIM_VERSION
 - MBB_MBIM_VERSION
---

# _MBB_MBIM_VERSION enumeration


## -description

The **MBB_MBIM_VERSION** enumeration defines the version of the MBIM specification that a client driver and its device support.

## -enum-fields

### -field MbbMbimVersion1Dot0 

The client driver and device support the MBIM specification Rev 1.0.

### -field MbbMbimVersion1Dot0Errata 

The client driver and device support the MBIM specification Rev 1.0 Errata-1.

## -remarks

Client drivers set the MBIM specification version they support in the **Version** member of the [**MBB_DEVICE_MBIM_PARAMETERS**](ns-mbbcx-_mbb_device_mbim_parameters.md) structure. 

Currently, client drivers must set the value of this field to **MbbMbimVersion1Dot0Errata**.

## -see-also

