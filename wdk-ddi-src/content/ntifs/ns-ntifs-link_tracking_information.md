---
UID: NS:ntifs._LINK_TRACKING_INFORMATION
tech.root: ifsk
title: LINK_TRACKING_INFORMATION
ms.date: 03/13/2023
targetos: Windows
description: Learn more about the LINK_TRACKING_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: LINK_TRACKING_INFORMATION, *PLINK_TRACKING_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _LINK_TRACKING_INFORMATION
 - PLINK_TRACKING_INFORMATION
 - LINK_TRACKING_INFORMATION
f1_keywords:
 - _LINK_TRACKING_INFORMATION
 - ntifs/_LINK_TRACKING_INFORMATION
 - PLINK_TRACKING_INFORMATION
 - ntifs/PLINK_TRACKING_INFORMATION
 - LINK_TRACKING_INFORMATION
 - ntifs/LINK_TRACKING_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _LINK_TRACKING_INFORMATION
---

## -description

The **LINK_TRACKING_INFORMATION** structure contains the link tracking information of the file.

## -struct-fields

### -field Type

A [**LINK_TRACKING_INFORMATION_TYPE**](ne-ntifs-link_tracking_information_type.md) value that specifies the type of file system that the file resides on.

### -field VolumeId[16]

An unsigned character array that holds the volume identifier.

## -remarks

## -see-also

[**FSCTL_LMR_GET_LINK_TRACKING_INFORMATION**](/windows-hardware/drivers/ifs/fsctl-lmr-get-link-tracking-information)