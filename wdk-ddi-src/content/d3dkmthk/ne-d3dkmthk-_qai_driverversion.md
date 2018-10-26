---
UID: NE:d3dkmthk._QAI_DRIVERVERSION
title: "_QAI_DRIVERVERSION"
author: windows-driver-content
description: The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports.
old-location: display\d3dkmt_driverversion.htm
ms.assetid: 12ac73ed-f829-4f22-bca9-ccc1dc29f4c4
ms.date: 05/10/2018
ms.keywords: D3DKMT_DRIVERVERSION, D3DKMT_DRIVERVERSION enumeration [Display Devices], KMT_DRIVERVERSION_WDDM_1_0, KMT_DRIVERVERSION_WDDM_1_1, KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE, KMT_DRIVERVERSION_WDDM_1_2, KMT_DRIVERVERSION_WDDM_1_3, KMT_DRIVERVERSION_WDDM_2_0, OpenGL_Structs_2f7fe9d6-ec67-46b1-9c05-51d06d186fe1.xml, _QAI_DRIVERVERSION, _QAI_DRIVERVERSION enumeration [Display Devices], d3dkmthk/, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_0, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_1, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_2, d3dkmthk/KMT_DRIVERVERSION_WDDM_1_3, d3dkmthk/KMT_DRIVERVERSION_WDDM_2_0, d3dkmthk/_QAI_DRIVERVERSION, display.d3dkmt_driverversion
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_DRIVERVERSION is supported beginning with the Windows 7 operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_DRIVERVERSION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DRIVERVERSION
---

# _QAI_DRIVERVERSION enumeration


## -description


The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports.


## -syntax


```cpp
typedef enum _QAI_DRIVERVERSION {
  KMT_DRIVERVERSION_WDDM_1_0             = 1000,
  KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE  = 1102,
  KMT_DRIVERVERSION_WDDM_1_1             = 1105,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  KMT_DRIVERVERSION_WDDM_1_2             = 1200,
#endif
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  KMT_DRIVERVERSION_WDDM_1_3             = 1300,
#endif
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  KMT_DRIVERVERSION_WDDM_2_0             = 2000,
#endif

} D3DKMT_DRIVERVERSION;
```


## -enum-fields




### -field KMT_DRIVERVERSION_WDDM_1_0

The display miniport driver supports the Windows Vista display driver model (WDDM) without Windows 7 features.


### -field KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE

The display miniport driver supports the Windows Vista display driver model with prereleased Windows 7 features.


### -field KMT_DRIVERVERSION_WDDM_1_1

The display miniport driver supports the Windows Vista display driver model with released Windows 7 features.


### -field KMT_DRIVERVERSION_WDDM_1_2

The display miniport driver supports the Windows Vista display driver model with released Windows 8 features.

Supported starting with Windows 8.


### -field KMT_DRIVERVERSION_WDDM_1_3

The display miniport driver supports the Windows display driver model with released Windows 8.1 features.

Supported starting with Windows 8.1.


### -field KMT_DRIVERVERSION_WDDM_2_0

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10.


### -field KMT_DRIVERVERSION_WDDM_2_1

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10, version 1607.

### -field KMT_DRIVERVERSION_WDDM_2_2

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10, version 1703.

### -field KMT_DRIVERVERSION_WDDM_2_3

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10, version 1709.

### -field KMT_DRIVERVERSION_WDDM_2_4

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10, version 1803.

### -field KMT_DRIVERVERSION_WDDM_2_5

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10, version 1809.

## -remarks



The <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a> returns a D3DKMT_DRIVERVERSION value in a variable that the <b>pPrivateDriverData</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a> structure points to when the OpenGL installable client driver (ICD) sets the <b>Type</b> member of <b>D3DKMT_QUERYADAPTERINFO</b> to KMTQAITYPE_DRIVERVERSION.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>



 

 


