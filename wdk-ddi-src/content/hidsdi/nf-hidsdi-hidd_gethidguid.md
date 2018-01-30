---
UID: NF:hidsdi.HidD_GetHidGuid
title: HidD_GetHidGuid function
author: windows-driver-content
description: The HidD_GetHidGuid routine returns the device interfaceGUID for HIDClass devices.
old-location: hid\hidd_gethidguid.htm
old-project: hid
ms.assetid: 552b607e-65c7-4595-9adb-b9c2f4301afd
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidsdi/HidD_GetHidGuid, HidD_GetHidGuid, hid.hidd_gethidguid, HidD_GetHidGuid routine [Human Input Devices], hidfunc_61242b6f-b794-48c7-84b8-ef8d0d4e69af.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hid.dll
apiname:
-	HidD_GetHidGuid
product: Windows
targetos: Windows
req.typenames: "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION"
---

# HidD_GetHidGuid function


## -description


The <b>HidD_GetHidGuid</b> routine returns the <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device interface</a><a href="https://msdn.microsoft.com/library/windows/hardware/dn922935">GUID</a> for HIDClass devices.


## -syntax


````
void __stdcall HidD_GetHidGuid(
  _Out_ LPGUID HidGuid
);
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetHidGuid routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

