---
UID: NS:d3dkmdt._DXGK_MONITORLINKINFO_USAGEHINTS
title: "_DXGK_MONITORLINKINFO_USAGEHINTS"
author: windows-driver-content
description: Hints to the driver on the intended usage of the display device.
old-location: display\dxgk_monitorlinkinfo_usagehints.htm
old-project: display
ms.assetid: 4FC2509A-9983-41F8-901F-60DCEDBC163F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_monitorlinkinfo_usagehints, d3dkmdt/DXGK_MONITORLINKINFO_USAGEHINTS, PDXGK_MONITORLINKINFO_USAGEHINTS, _DXGK_MONITORLINKINFO_USAGEHINTS, PDXGK_MONITORLINKINFO_USAGEHINTS union pointer [Display Devices], *PDXGK_MONITORLINKINFO_USAGEHINTS, DXGK_MONITORLINKINFO_USAGEHINTS union [Display Devices], d3dkmdt/PDXGK_MONITORLINKINFO_USAGEHINTS, DXGK_MONITORLINKINFO_USAGEHINTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGK_MONITORLINKINFO_USAGEHINTS
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORLINKINFO_USAGEHINTS, *PDXGK_MONITORLINKINFO_USAGEHINTS
---

# _DXGK_MONITORLINKINFO_USAGEHINTS structure


## -description


Hints to the driver on the intended usage of the display device.


## -syntax


````
typedef union _DXGK_MONITORLINKINFO_USAGEHINTS {
  UINT Hidden;
  UINT Reserved ;
} DXGK_MONITORLINKINFO_USAGEHINTS, *PDXGK_MONITORLINKINFO_USAGEHINTS;
````


## -struct-fields




#### - Hidden

If TRUE, DxgKrnl will hide this display from Win32 so it cannot be a part of the desktop.


#### - Reserved

This value is reserved for system use.


### -field Value

 


