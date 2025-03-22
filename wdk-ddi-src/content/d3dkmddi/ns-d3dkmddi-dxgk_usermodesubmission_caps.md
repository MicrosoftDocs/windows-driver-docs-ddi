---
UID: NS:d3dkmddi._DXGK_USERMODESUBMISSION_CAPS
tech.root: display
title: DXGK_USERMODESUBMISSION_CAPS
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the DXGK_USERMODESUBMISSION_CAPS structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_USERMODESUBMISSION_CAPS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_USERMODESUBMISSION_CAPS
 - DXGK_USERMODESUBMISSION_CAPS
f1_keywords:
 - _DXGK_USERMODESUBMISSION_CAPS
 - d3dkmddi/_DXGK_USERMODESUBMISSION_CAPS
 - DXGK_USERMODESUBMISSION_CAPS
 - d3dkmddi/DXGK_USERMODESUBMISSION_CAPS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_USERMODESUBMISSION_CAPS
---

# DXGK_USERMODESUBMISSION_CAPS structure (d3dkmddi.h)

## -description

The **DXGK_USERMODESUBMISSION_CAPS** structure describes KMD's user-mode work submission capabilities.

## -struct-fields

### -field Flags

Contains flags that describe the capabilities of the KMD's user-mode work submission.

### -field Flags.SecondaryDoorbellSupported

When set, the KMD supports a secondary doorbell for user-mode work submission.

### -field Flags.Reserved

Reserved for system use.

### -field Flags.Value

An alternative way to access the structure members.

### -field DoorbellSizeInBytes

The memory size of the doorbell, in bytes.

### -field SecondaryDoorbellSizeInBytes

The memory size of the secondary doorbell, in bytes.

### -field Reserved[16]

Reserved for system use.

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**DXGK_QUERYADAPTERINFOTYPE**](ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
