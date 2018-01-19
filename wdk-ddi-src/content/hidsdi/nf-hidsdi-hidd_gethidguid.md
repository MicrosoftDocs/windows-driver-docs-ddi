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
ms.keywords: HidD_GetHidGuid
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
req.alt-api: HidD_GetHidGuid
req.alt-loc: Hid.dll
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
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---

# HidD_GetHidGuid function



## -description
The <b>HidD_GetHidGuid</b> routine returns the <a href="wdkgloss.d#wdkgloss.device_interface#wdkgloss.device_interface"><i>device interface</i></a><a href="wdkgloss.g#wdkgloss.guid#wdkgloss.guid"><i>GUID</i></a> for HIDClass devices.



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
<dl>
<dt>
<a href="..\wdm\nf-wdm-iogetdeviceinterfaces.md">IoGetDeviceInterfaces</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetHidGuid routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

