---
UID: NS:d3dhal._DD_FREE_DEFERRED_AGP_DATA
title: "_DD_FREE_DEFERRED_AGP_DATA"
author: windows-driver-content
description: DirectX 8.0 and later versions and NT-based operating systems only. DD_FREE_DEFERRED_AGP_DATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for D3DGDI2_TYPE_DEFER_AGP_FREES and D3DGDI2_TYPE_FREE_DEFERRED_AGP notifications.
old-location: display\dd_free_deferred_agp_data.htm
old-project: display
ms.assetid: 38830856-1f66-44d6-9501-9454a31571b7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DD_FREE_DEFERRED_AGP_DATA, d3dhal/DD_FREE_DEFERRED_AGP_DATA, _DD_FREE_DEFERRED_AGP_DATA, DD_FREE_DEFERRED_AGP_DATA structure [Display Devices], d3dstrct_06ad77f0-33c0-4297-a713-d23f0684dbee.xml, display.dd_free_deferred_agp_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
-	d3dhal.h
apiname:
-	DD_FREE_DEFERRED_AGP_DATA
product: Windows
targetos: Windows
req.typenames: DD_FREE_DEFERRED_AGP_DATA
---

# _DD_FREE_DEFERRED_AGP_DATA structure


## -description



   DirectX 8.0 and later versions and NT-based operating systems only.
   

DD_FREE_DEFERRED_AGP_DATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for D3DGDI2_TYPE_DEFER_AGP_FREES and D3DGDI2_TYPE_FREE_DEFERRED_AGP notifications.


## -syntax


````
typedef struct _DD_FREE_DEFERRED_AGP_DATA {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwProcessId;
} DD_FREE_DEFERRED_AGP_DATA;
````


## -struct-fields




### -field gdi2

Specifies a <a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field dwProcessId

Specifies the process identifier (PID) of the process destroying the <a href="https://msdn.microsoft.com/05a2f942-4374-421e-8292-d122f9fe3571">AGP memory</a> for surfaces.


## -remarks


The driver sometimes receives a <b>GetDriverInfo2</b> call with D3DGDI2_TYPE_DEFER_AGP_FREES notification type before a display mode change occurs. The runtime only sends this notification type if it is to be used to perform the display mode change. Drivers should check the process identifier (PID) of the process destroying the surface against the process that created the surface. If the PIDs are different, the driver probably should not destroy the user-mode mappings of the AGP memory because an application might still be using the memory.

The driver receives a <b>GetDriverInfo2</b> call with D3DGDI2_TYPE_FREE_DEFERRED_AGP notification type when all display devices within the process stop using surfaces, textures, vertex buffers, and index buffers that were locked at the time of the display mode change. This notification type informs the driver that it is now safe to destroy all the user-mode mappings of the AGP memory. 



## -see-also

<a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_FREE_DEFERRED_AGP_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

