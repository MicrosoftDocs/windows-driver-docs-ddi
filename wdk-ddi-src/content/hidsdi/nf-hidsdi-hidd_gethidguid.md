---
UID: NF:hidsdi.HidD_GetHidGuid
title: HidD_GetHidGuid function
author: windows-driver-content
description: The HidD_GetHidGuid routine returns the device interfaceGUID for HIDClass devices.
old-location: hid\hidd_gethidguid.htm
old-project: hid
ms.assetid: 552b607e-65c7-4595-9adb-b9c2f4301afd
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: HidD_GetHidGuid, HidD_GetHidGuid routine [Human Input Devices], hid.hidd_gethidguid, hidfunc_61242b6f-b794-48c7-84b8-ef8d0d4e69af.xml, hidsdi/HidD_GetHidGuid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hid.dll
api_name:
-	HidD_GetHidGuid
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidD_GetHidGuid function


## -description


The <b>HidD_GetHidGuid</b> routine returns the <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device interface</a><a href="https://msdn.microsoft.com/library/windows/hardware/dn922935">GUID</a> for HIDClass devices.


## -parameters




### -param HidGuid [out]

Pointer to a caller-allocated GUID buffer that the routine uses to return the device interface GUID for HIDClass devices.


## -returns



None.




## -remarks



Only user-mode applications can call <b>HidD_GetHidGuid</b>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>
 

 

