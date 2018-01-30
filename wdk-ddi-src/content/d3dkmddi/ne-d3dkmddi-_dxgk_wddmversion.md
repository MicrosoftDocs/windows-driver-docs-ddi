---
UID: NE:d3dkmddi._DXGK_WDDMVERSION
title: "_DXGK_WDDMVERSION"
author: windows-driver-content
description: The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.
old-location: display\dxgk_wddmversion.htm
old-project: display
ms.assetid: 2360224a-fa99-4b2c-a346-0129e3e95cd7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_WDDMVERSION enumeration [Display Devices], d3dkmddi/DXGKDDI_WDDMv2, d3dkmddi/DXGKDDI_WDDMv1_2, _DXGK_WDDMVERSION, display.dxgk_wddmversion, DXGKDDI_WDDMv2, DmEnums_3a73843a-4967-4faa-a217-42487ae4f865.xml, DXGK_WDDMVERSION, DXGKDDI_WDDMv1_2, d3dkmddi/DXGK_WDDMVERSION, DXGKDDI_WDDMv1, d3dkmddi/DXGKDDI_WDDMv1
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_WDDMVERSION
product: Windows
targetos: Windows
req.typenames: DXGK_WDDMVERSION
---

# _DXGK_WDDMVERSION enumeration


## -description


The DXGK_WDDMVERSION enumeration is reserved for system use. Except for the case noted below, do not use it in your driver.


## -syntax


````
typedef enum _DXGK_WDDMVERSION { 
  DXGKDDI_WDDMv1    = 0x1000,
  DXGKDDI_WDDMv1_2  = 0x1200,
  DXGKDDI_WDDMv2    = 0x2000
} DXGK_WDDMVERSION;
````


## -enum-fields




### -field DXGKDDI_WDDMv1

Reserved for system use.


<div class="alert"><b>Note</b>  If a driver does not support Windows 7 features (DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), set the <b>WDDMVersion</b> member of the  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure to DXGKDDI_WDDMv1.</div>
<div> </div>



### -field DXGKDDI_WDDMv1_2

Supported beginning with Windows 8.

Reserved for system use.


### -field DXGKDDI_WDDMv1_3



### -field DXGKDDI_WDDMv2

Reserved for system use.


### -field DXGKDDI_WDDMv2_1



### -field DXGKDDI_WDDMv2_2



### -field DXGKDDI_WDDMv2_3




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_WDDMVERSION enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

