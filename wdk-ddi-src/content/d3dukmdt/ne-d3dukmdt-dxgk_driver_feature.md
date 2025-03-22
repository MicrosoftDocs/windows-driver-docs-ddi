---
UID: NE:d3dukmdt._DXGK_DRIVER_FEATURE
tech.root: display
title: DXGK_DRIVER_FEATURE
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGK_DRIVER_FEATURE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _DXGK_DRIVER_FEATURE
 - DXGK_DRIVER_FEATURE
f1_keywords:
 - _DXGK_DRIVER_FEATURE
 - d3dukmdt/_DXGK_DRIVER_FEATURE
 - DXGK_DRIVER_FEATURE
 - d3dukmdt/DXGK_DRIVER_FEATURE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DRIVER_FEATURE
---

# DXGK_DRIVER_FEATURE enumeration (d3dukmdt.h)

## -description

The **DXGK_DRIVER_FEATURE** enumeration is a list of driver features.

## -enum-fields

### -field DXGK_DRIVER_FEATURE_HWSCH:0

The hardware accelerated GPU scheduling feature.

### -field DXGK_DRIVER_FEATURE_HWFLIPQUEUE:1

The hardware flip queue feature.

### -field DXGK_DRIVER_FEATURE_LDA_GPUPV:2

The linked display adapter in GPU paravirtualization feature.

### -field DXGK_DRIVER_FEATURE_KMD_SIGNAL_CPU_EVENT:3

The signaling of a CPU event by KMD feature.

### -field DXGK_DRIVER_FEATURE_USER_MODE_SUBMISSION:4

The user-mode submission feature.

### -field DXGK_DRIVER_FEATURE_SHARE_BACKING_STORE_WITH_KMD:5

The allowing UMD to share the backing store with KMD feature.

### -field DXGK_DRIVER_FEATURE_RESERVED_1:6

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_2:7

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_3:8

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_4:9

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_5:10

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_6:11

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_7:12

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_8:13

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_9:14

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_10:15

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_11:16

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_12:17

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_13:18

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_14:19

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_15:20

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_16:21

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_17:22

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_18:23

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_19:24

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_20:25

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_21:26

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_22:27

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_23:28

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_24:29

Reserved.

### -field DXGK_DRIVER_FEATURE_RESERVED_25:30

Reserved.

### -field DXGK_DRIVER_FEATURE_SAMPLE:31

### -field DXGK_DRIVER_FEATURE_PAGE_BASED_MEMORY_MANAGER:32

The page-based memory management feature.

### -field DXGK_DRIVER_FEATURE_KERNEL_MODE_TESTING:33

The kernel-mode testing interface feature.

### -field DXGK_DRIVER_FEATURE_64K_PT_DEMOTION_FIX:34

The OS bugfix for 64K page table demotion.

### -field DXGK_DRIVER_FEATURE_GPUPV_PRESENT_HWQUEUE:35

The OS bugfix for GPU paravirtualization and hardware scheduling enabled.

### -field DXGK_DRIVER_FEATURE_GPUVAIOMMU:36

The usage of GPU virtual addresses with IoMmu feature.

### -field DXGK_DRIVER_FEATURE_NATIVE_FENCE:37

The native GPU fence feature.

### -field DXGK_DRIVER_FEATURE_MAX

Maximum value for the enumeration.

## -remarks

A WDDM feature is identified by a [feature ID](ne-d3dukmdt-dxgk_feature_id.md) value that has a [feature category](ne-d3dukmdt-dxgk_feature_category.md) (upper 4 bits) and a sub-ID (bottom 28 bits). The feature sub-ID is one of the values in this enumeration when the feature category is **DXGK_FEATURE_CATEGORY_DRIVER**.

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_FEATURE_CATEGORY**](ne-d3dukmdt-dxgk_feature_category.md)

[**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md)
