---
UID: NE:d3dkmddi._DXGK_FEATURE_ID
title: DXGK_FEATURE_ID
description: Learn more about the DXGK_FEATURE_ID enumeration.
tech.root: display
ms.date: 09/07/2022
keywords: ["DXGK_FEATURE_ID enumeration"]
ms.keywords: _DXGK_FEATURE_ID, DXGK_FEATURE_ID,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DXGK_FEATURE_ID
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
f1_keywords:
 - _DXGK_FEATURE_ID
 - d3dkmddi/_DXGK_FEATURE_ID
 - DXGK_FEATURE_ID
 - d3dkmddi/DXGK_FEATURE_ID
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_FEATURE_ID
 - DXGK_FEATURE_ID
product:
 - Windows
dev_langs:
 - c++
---

# DXGK_FEATURE_ID enumeration

## -description

A kernel-mode driver (KMD) calls [**DXGKCB_ISFEATUREENABLED**](nc-d3dkmddi-dxgkcb_isfeatureenabled.md) with a **DXGK_FEATURE_ID** value to query whether the OS will allow it to enable support for that feature.

## -enum-fields

### -field DXGK_FEATURE_HWSCH:0

Query whether to enable support for hardware-accelerated GPU scheduling.

### -field DXGK_FEATURE_HWFLIPQUEUE:1

Query whether to enable support for the hardware flip queue feature. Available starting in Windows 11 (WDDM 3.0).

### -field DXGK_FEATURE_LDA_GPUPV:2

Query whether to enable support for linked device adapter (LDA) in GPU paravirtualization (GPU_PV). Available starting in Windows 11 (WDDM 3.0).

### -field DXGK_FEATURE_KMD_SIGNAL_CPU_EVENT:3

Query whether to enable support for signaling CPU events by KMD. Available starting in Windows 11 (WDDM 3.0).

### -field DXGK_FEATURE_USER_MODE_SUBMISSION:4

Query whether to enable user-mode submissions. Available starting in Windows 11 version 22H2 (WDDM 3.1).

### -field DXGK_FEATURE_SHARE_BACKING_STORE_WITH_KMD:5

Query whether to enable support to share the backing store with the KMD. Available starting in Windows 11 version 22H2 (WDDM 3.1).

### -field DXGK_FEATURE_RESERVED_1:6

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_2:7

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_3:8

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_4:9

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_5:10

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_6:11

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_7:12

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_8:13

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_9:14

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_10:15

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_11:16

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_12:17

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_13:18

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_14:19

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_15:20

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_16:21

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_17:22

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_18:23

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_19:24

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_20:25

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_21:26

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_22:27

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_23:28

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_24:29

Reserved for system use.

### -field DXGK_FEATURE_RESERVED_25:30

### -field DXGK_FEATURE_SAMPLE:31

Reserved for system use.

### -field DXGK_FEATURE_PAGE_BASED_MEMORY_MANAGER:32

Reserved for system use.

### -field DXGK_FEATURE_KERNEL_MODE_TESTING:33

Reserved for system use.

### -field DXGK_FEATURE_MAX

Maximum value for the **DXGK_FEATURE_ID** enumeration.

## -remarks

For each feature in this enumeration that the driver supports, the driver must do the following:

* Call the OS to query the feature's enabled status.
* Only enable the feature if the OS returned `Enabled=TRUE`.

Drivers that don't support the feature doesn't have to call the OS to query its status.

## -see-also

[**DXGKARGCB_ISFEATUREENABLED**](ns-d3dkmddi-_dxgkargcb_isfeatureenabled.md)

[**DXGKCB_ISFEATUREENABLED**](nc-d3dkmddi-dxgkcb_isfeatureenabled.md)
