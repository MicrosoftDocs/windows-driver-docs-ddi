---
UID: NE:d3dkmddi._DXGK_WDDMVERSION
title: _DXGK_WDDMVERSION (d3dkmddi.h)
description: The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.
old-location: display\dxgk_wddmversion.htm
ms.assetid: 2360224a-fa99-4b2c-a346-0129e3e95cd7
ms.date: 05/10/2018
ms.keywords: DXGKDDI_WDDMv1, DXGKDDI_WDDMv1_2, DXGKDDI_WDDMv2, DXGK_WDDMVERSION, DXGK_WDDMVERSION enumeration [Display Devices], DmEnums_3a73843a-4967-4faa-a217-42487ae4f865.xml, _DXGK_WDDMVERSION, d3dkmddi/DXGKDDI_WDDMv1, d3dkmddi/DXGKDDI_WDDMv1_2, d3dkmddi/DXGKDDI_WDDMv2, d3dkmddi/DXGK_WDDMVERSION, display.dxgk_wddmversion
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_WDDMVERSION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_WDDMVERSION
ms.custom: 19H1
---

# _DXGK_WDDMVERSION enumeration


## -description


The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.



## -syntax


```cpp
typedef enum _DXGK_WDDMVERSION {
  DXGKDDI_WDDMv1    = 0x1000,
  DXGKDDI_WDDMv1_2  = 0x1200,
  DXGKDDI_WDDMv2    = 0x2000
} DXGK_WDDMVERSION;
```



## -enum-fields




### -field DXGKDDI_WDDMv1

Reserved for system use.


<div class="alert"><b>Note</b>  If a driver does not support Windows 7 features (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), set the <b>WDDMVersion</b> member of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure to DXGKDDI_WDDMv1.</div>
<div> </div>



### -field DXGKDDI_WDDMv1_2

Supported beginning with Windows 8.

Reserved for system use.


### -field DXGKDDI_WDDMv1_3

Windows Display Driver Model for Windows 8.1.

### -field DXGKDDI_WDDMv2

Windows Display Driver Model for Windows 10, version 1507.


### -field DXGKDDI_WDDMv2_1

Windows Display Driver Model for Windows 10, version 1607.

### -field DXGKDDI_WDDMv2_1_5

### -field DXGKDDI_WDDMv2_1_6

### -field DXGKDDI_WDDMv2_2

Windows Display Driver Model for Windows 10, version 1703.

### -field DXGKDDI_WDDMv2_3

Windows Display Driver Model for Windows 10, version 1709.

### -field DXGKDDI_WDDMv2_4

Windows Display Driver Model for Windows 10, version 1803.

### -field DXGKDDI_WDDMv2_5

Windows Display Driver Model for Windows 10, version 1809.

### -field DXGKDDI_WDDMv2_6

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPn Interface</a>
 

 

