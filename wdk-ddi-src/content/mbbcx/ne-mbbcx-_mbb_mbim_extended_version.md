---
UID: NE:mbbcx._MBB_MBIM_EXTENDED_VERSION
title: _MBB_MBIM_EXTENDED_VERSION (mbbcx.h)
description: The MBB_MBIM_EXTENDED_VERSION enumeration defines the version of the extended MBIM specification that a client driver and its device support. 
tech.root: netvista
ms.assetid: 38F07398-3659-46A3-A0E6-FAD5B18E0934
ms.date: 09/27/2019
keywords: ["_MBB_MBIM_EXTENDED_VERSION enumeration"]
f1_keywords:
 - "mbbcx/-	_MBB_MBIM_EXTENDED_VERSION"
 - "-	_MBB_MBIM_EXTENDED_VERSION"
ms.keywords: _MBB_MBIM_EXTENDED_VERSION, MBB_MBIM_EXTENDED_VERSION, 
req.header: mbbcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: MBB_MBIM_EXTENDED_VERSION
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- mbbcx.h
api_name: 
- _MBB_MBIM_EXTENDED_VERSION
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _MBB_MBIM_EXTENDED_VERSION enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1809.

The **MBB_MBIM_EXTENDED_VERSION** enumeration defines the version of the extended MBIM specification that a client driver and its device support. 

## -enum-fields

### -field MbbMbimExtendedVersion1Dot0 

The client driver and device support the extended MBIM specification Rev 1.0.

### -field MbbMbimExtendedVersion2Dot0

The client driver and device support the extended MBIM specification Rev 2.0.

### -field MbbMbimExtendedVersion3Dot0

The client driver and device support the extended MBIM specification Rev 3.0.

## -remarks

Client drivers set the lowest MBIM specification extended version they support in the **ExtendedVersion** member of the [**MBB_DEVICE_MBIM_PARAMETERS**](ns-mbbcx-_mbb_device_mbim_parameters.md) structure. 

## -see-also
