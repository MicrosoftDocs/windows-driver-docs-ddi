---
UID: NE:d3dkmddi._DXGK_WDDMVERSION
title: DXGK_WDDMVERSION (d3dkmddi.h)
description: The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.
old-location: display\dxgk_wddmversion.htm
ms.date: 04/26/2022
keywords: ["DXGK_WDDMVERSION enumeration"]
ms.keywords: DXGKDDI_WDDMv1, DXGKDDI_WDDMv1_2, DXGKDDI_WDDMv2, DXGK_WDDMVERSION, DXGK_WDDMVERSION enumeration [Display Devices], DmEnums_3a73843a-4967-4faa-a217-42487ae4f865.xml, _DXGK_WDDMVERSION, d3dkmddi/DXGKDDI_WDDMv1, d3dkmddi/DXGKDDI_WDDMv1_2, d3dkmddi/DXGKDDI_WDDMv2, d3dkmddi/DXGK_WDDMVERSION, display.dxgk_wddmversion
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: DXGK_WDDMVERSION
ms.custom: 19H1
f1_keywords:
 - _DXGK_WDDMVERSION
 - d3dkmddi/_DXGK_WDDMVERSION
 - DXGK_WDDMVERSION
 - d3dkmddi/DXGK_WDDMVERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_WDDMVERSION
 - DXGK_WDDMVERSION
dev_langs:
 - c++
---

# DXGK_WDDMVERSION enumeration

## -description

The **DXGK_WDDMVERSION** enumeration identifies the Windows Display Driver Model (WDDM) version. It is reserved for system use. Except for the case noted below, do not use it in your driver.

## -enum-fields

### -field DXGKDDI_WDDMv1

Reserved for system use. NOTE: If a driver does not support Windows 7 features (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver with the Windows 7 WDK (Version 7600), set the **WDDMVersion** member of the [**DXGK_DRIVERCAPS**](./ns-d3dkmddi-_dxgk_drivercaps.md) structure to DXGKDDI_WDDMv1.

### -field DXGKDDI_WDDMv1_2

Reserved for system use. Supported beginning with Windows 8.

### -field DXGKDDI_WDDMv1_3

WDDM version for Windows 8.1.

### -field DXGKDDI_WDDMv2

WDDM version for Windows 10, version 1507.

### -field DXGKDDI_WDDMv2_1

WDDM version for Windows 10, version 1607.

### -field DXGKDDI_WDDMv2_1_5

### -field DXGKDDI_WDDMv2_1_6

### -field DXGKDDI_WDDMv2_2

WDDM version for Windows 10, version 1703.

### -field DXGKDDI_WDDMv2_3

WDDM version for Windows 10, version 1709.

### -field DXGKDDI_WDDMv2_4

WDDM version for Windows 10, version 1803.

### -field DXGKDDI_WDDMv2_5

WDDM version for Windows 10, version 1809.

### -field DXGKDDI_WDDMv2_6

WDDM version for Windows 10, version 1903.

### -field DXGKDDI_WDDMv2_7

WDDM version for Windows 10, version 2004.

### -field DXGKDDI_WDDMv2_8

WDDM version for Windows 10, Insider Preview Manganese.

### -field DXGKDDI_WDDMv2_9

WDDM version for Windows Server 2022.

### -field DXGKDDI_WDDMv3_0

WDDM version for Windows 11.

### -field DXGKDDI_WDDMv3_1

WDDM version for Windows 11, version 22H2.

### -field DXGKDDI_WDDM_LATEST

The latest version of WDDM. **DXGK_WDDMVERSION** cannot be greater than **DXGKDDI_WDDM_LATEST**.

## -see-also

[**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md)

[**DXGK_WDDMDEVICECAPS**](ns-d3dkmddi-_dxgk_wddmdevicecaps.md)
