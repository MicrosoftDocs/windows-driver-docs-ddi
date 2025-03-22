---
UID: NE:d3dukmdt._DXGK_FEATURE_CATEGORY
tech.root: display
title: DXGK_FEATURE_CATEGORY
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGK_FEATURE_CATEGORY enumeration.
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
 - _DXGK_FEATURE_CATEGORY
 - DXGK_FEATURE_CATEGORY
f1_keywords:
 - _DXGK_FEATURE_CATEGORY
 - d3dukmdt/_DXGK_FEATURE_CATEGORY
 - DXGK_FEATURE_CATEGORY
 - d3dukmdt/DXGK_FEATURE_CATEGORY
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_FEATURE_CATEGORY
---

# DXGK_FEATURE_CATEGORY enumeration (d3dukmdt.h)

## -description

The **DXGK_FEATURE_CATEGORY** enumeration specifies the category of a WDDM feature.

## -enum-fields

### -field DXGK_FEATURE_CATEGORY_DRIVER:0

Indicates a feature that requires additional driver support. For ease of implementation, the driver category is category 0 (meaning all 4 upper category ID bits are 0). This layout makes it easier for drivers to implement by allowing feature data to be store in static and/or linear arrays of data.

### -field DXGK_FEATURE_CATEGORY_OS:1

Indicates a feature that is internal or specific to the OS.

### -field DXGK_FEATURE_CATEGORY_BUGFIX:2

Indicates a bugfix. This value allows the driver or another component to trivially ask the OS if a bugfix is present. Drivers then don't have to do any fancy workarounds with build numbers, which can be confusing when backporting fixes.

### -field DXGK_FEATURE_CATEGORY_TEST:3

Reserved for testing purposes. No feature IDs in this category are used in production.

### -field DXGK_FEATURE_CATEGORY_RESERVED4:4

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED5:5

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED6:6

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED7:7

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED8:8

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED9:9

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED10:10

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED11:11

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED12:12

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED13:13

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED14:14

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_RESERVED15:15

Reserved for future use. No feature IDs are defined in this category.

### -field DXGK_FEATURE_CATEGORY_MAX:16

Maximum value for this enumeration.

## -remarks

A WDDM feature is identified by a [feature ID](ne-d3dukmdt-dxgk_feature_id.md) value that has a feature category (one of this enumeration's values in the upper 4 bits) and a sub-ID (bottom 28 bits).

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_DRIVER_FEATURE**](ne-d3dukmdt-dxgk_driver_feature.md)

[**DXGK_FEATURE_ID**](ne-d3dukmdt-dxgk_feature_id.md)
