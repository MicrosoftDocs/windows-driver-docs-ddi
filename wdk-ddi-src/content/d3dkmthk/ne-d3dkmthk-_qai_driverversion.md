---
UID: NE:d3dkmthk._QAI_DRIVERVERSION
title: QAI_DRIVERVERSION (d3dkmthk.h)
description: The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports.
old-location: display\d3dkmt_driverversion.htm
ms.date: 02/23/2022
keywords: ["QAI_DRIVERVERSION enumeration"]
ms.keywords: D3DKMT_DRIVERVERSION, D3DKMT_DRIVERVERSION enumeration [Display Devices], KMT_DRIVERVERSION_WDDM_1_0, KMT_DRIVERVERSION_WDDM_1_1, KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE, KMT_DRIVERVERSION_WDDM_1_2, KMT_DRIVERVERSION_WDDM_1_3, KMT_DRIVERVERSION_WDDM_2_0, OpenGL_Structs_2f7fe9d6-ec67-46b1-9c05-51d06d186fe1.xml, _QAI_DRIVERVERSION, _QAI_DRIVERVERSION enumeration [Display Devices], d3dkmthk/, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_0, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_1, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_2, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_3, d3dkmthk/KMT_DRIVERVERSION_WDDM_2_0, d3dkmthk/_QAI_DRIVERVERSION, display.d3dkmt_driverversion
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DRIVERVERSION
ms.custom: 19H1
f1_keywords:
 - _QAI_DRIVERVERSION
 - d3dkmthk/_QAI_DRIVERVERSION
 - D3DKMT_DRIVERVERSION
 - d3dkmthk/D3DKMT_DRIVERVERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _QAI_DRIVERVERSION
 - D3DKMT_DRIVERVERSION
product:
 - Windows
dev_langs:
 - c++
---

# QAI_DRIVERVERSION enumeration

## -description

The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports.

## -enum-fields

### -field KMT_DRIVERVERSION_WDDM_1_0

The display miniport driver supports the Windows Vista display driver model (WDDM) without Windows 7 features.

### -field KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE

The display miniport driver supports the Windows Vista display driver model with prereleased Windows 7 features.

### -field KMT_DRIVERVERSION_WDDM_1_1

The display miniport driver supports the Windows Vista display driver model with released Windows 7 features.

### -field KMT_DRIVERVERSION_WDDM_1_2

The display miniport driver supports the Windows Vista display driver model with released Windows 8 features.

### -field KMT_DRIVERVERSION_WDDM_1_3

The display miniport driver supports the Windows display driver model with released Windows 8.1 features.

### -field KMT_DRIVERVERSION_WDDM_2_0

The display miniport driver supports the Windows display driver model with released Windows 10 features.

### -field KMT_DRIVERVERSION_WDDM_2_1

The display miniport driver supports the Windows display driver model with released Windows 10, version 1607 features.

### -field KMT_DRIVERVERSION_WDDM_2_2

The display miniport driver supports the Windows display driver model with released Windows 10, version 1703 features.

### -field KMT_DRIVERVERSION_WDDM_2_3

The display miniport driver supports the Windows display driver model with released Windows 10, version 1709 features.

### -field KMT_DRIVERVERSION_WDDM_2_4

The display miniport driver supports the Windows display driver model with released Windows 10, version 1803 features.

### -field KMT_DRIVERVERSION_WDDM_2_5

The display miniport driver supports the Windows display driver model with released Windows 10, version 1809 features.

### -field KMT_DRIVERVERSION_WDDM_2_6

The display miniport driver supports the Windows display driver model with released Windows 10, version 1903 features.

### -field KMT_DRIVERVERSION_WDDM_2_7

The display miniport driver supports the Windows display driver model with released Windows 10, version 2004 features.

### -field KMT_DRIVERVERSION_WDDM_2_8

The display miniport driver supports the Windows display driver model with released Windows 10, version 2004 features.

### -field KMT_DRIVERVERSION_WDDM_2_9

The display miniport driver supports the Windows display driver model with released Windows Server 2022 features.

### -field KMT_DRIVERVERSION_WDDM_3_0

The display miniport driver supports the Windows display driver model with released Windows 11, version 21H2 features.

### -field KMT_DRIVERVERSION_WDDM_3_1

The display miniport driver supports the Windows display driver model with released Windows 11, version 21H2 features.

## -remarks

The [**D3DKMTQueryAdapterInfo**](..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md) returns a **D3DKMT_DRIVERVERSION** value in a variable that the **pPrivateDriverData** member of the [**D3DKMT_QUERYADAPTERINFO**](..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md) structure points to when the OpenGL installable client driver (ICD) sets the **Type** member of **D3DKMT_QUERYADAPTERINFO** to KMTQAITYPE_DRIVERVERSION.

## -see-also

[**D3DKMT_QUERYADAPTERINFO**](..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)

[**D3DKMTQueryAdapterInfo**](..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
