---
UID: NS:d3dkmddi._DXGK_VIDPNSOURCEMODESET_INTERFACE
title: "_DXGK_VIDPNSOURCEMODESET_INTERFACE" (d3dkmddi.h)
description: The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Source Mode Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpnsourcemodeset_interface.htm
ms.assetid: c608643f-e791-44b8-8719-4e98e10fa7b0
ms.date: 10/30/2018
ms.keywords: DXGK_VIDPNSOURCEMODESET_INTERFACE, DXGK_VIDPNSOURCEMODESET_INTERFACE structure [Display Devices], DmStructs_8e8b4b99-8121-4cff-9d1b-f88a9041e7cd.xml, _DXGK_VIDPNSOURCEMODESET_INTERFACE, d3dkmddi/DXGK_VIDPNSOURCEMODESET_INTERFACE, display.dxgk_vidpnsourcemodeset_interface
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmddi.h
api_name:
-	DXGK_VIDPNSOURCEMODESET_INTERFACE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDPNSOURCEMODESET_INTERFACE
---

# _DXGK_VIDPNSOURCEMODESET_INTERFACE structure


## -description


The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Source mode set interface in [VidPN Objects and Interfaces](https://docs.microsoft.com/windows-hardware/drivers/display/vidpn-objects-and-interfaces), which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field pfnGetNumModes

A pointer to the <a href="https://msdn.microsoft.com/abdc053c-45da-4af3-84c1-7eeb4a2856cb">pfnGetNumModes</a> function.


### -field pfnAcquireFirstModeInfo

A pointer to the <a href="https://msdn.microsoft.com/3af816e0-f1a4-4477-8735-6400aadfb57b">pfnAcquireFirstModeInfo</a> function.


### -field pfnAcquireNextModeInfo

A pointer to the <a href="https://msdn.microsoft.com/d9cb1ff1-c428-46e5-884a-5fc39e16300e">pfnAcquireNextModeInfo</a> function.


### -field pfnAcquirePinnedModeInfo

A pointer to the <a href="https://msdn.microsoft.com/e757852b-ee68-4b07-83c8-9dfd089d1ab7">pfnAcquirePinnedModeInfo</a> function.


### -field pfnReleaseModeInfo

A pointer to the <a href="https://msdn.microsoft.com/614283cc-90bf-44f2-bab2-1aeec5e7de01">pfnReleaseModeInfo</a> function.


### -field pfnCreateNewModeInfo

A pointer to the <a href="https://msdn.microsoft.com/b18aab68-7457-45eb-8641-0b6180cfa70e">pfnCreateNewModeInfo</a> function.


### -field pfnAddMode

A pointer to the <a href="https://msdn.microsoft.com/754078c2-f79b-4237-a14c-96903856f3a5">pfnAddMode</a> function.


### -field pfnPinMode

A pointer to the <a href="https://msdn.microsoft.com/14bbdc35-e633-49a5-bdf0-6b60d330ca8e">pfnPinMode</a> function.


## -remarks



The display miniport driver calls the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn interface</a> to obtain a handle to a VidPN source mode set object and a pointer to a DXGK_VIDPNSOURCEMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN source mode set object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561921">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562082">DXGK_VIDPNTARGETMODESET_INTERFACE</a>



<a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a>
 

 

