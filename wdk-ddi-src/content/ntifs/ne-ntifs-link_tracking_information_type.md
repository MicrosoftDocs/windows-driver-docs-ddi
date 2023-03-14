---
UID: NE:ntifs._LINK_TRACKING_INFORMATION_TYPE
tech.root: ifsk
title: LINK_TRACKING_INFORMATION_TYPE
ms.date: 03/08/2023
targetos: Windows
description: Learn more about the LINK_TRACKING_INFORMATION_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _LINK_TRACKING_INFORMATION_TYPE
 - PLINK_TRACKING_INFORMATION_TYPE
 - LINK_TRACKING_INFORMATION_TYPE
f1_keywords:
 - _LINK_TRACKING_INFORMATION_TYPE
 - ntifs/_LINK_TRACKING_INFORMATION_TYPE
 - PLINK_TRACKING_INFORMATION_TYPE
 - ntifs/PLINK_TRACKING_INFORMATION_TYPE
 - LINK_TRACKING_INFORMATION_TYPE
 - ntifs/LINK_TRACKING_INFORMATION_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _LINK_TRACKING_INFORMATION_TYPE
---

## -description

A **LINK_TRACKING_INFORMATION_TYPE** value identifies the type of file system that a file resides on.

## -enum-fields

### -field NtfsLinkTrackingInformation

The file resides on a distributed file system.

### -field DfsLinkTrackingInformation

The file resides on an NTFS file system.

## -see-also

[**LINK_TRACKING_INFORMATION**](ns-ntifs-link_tracking_information.md)
