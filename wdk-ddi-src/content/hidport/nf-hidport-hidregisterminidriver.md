---
UID: NF:hidport.HidRegisterMinidriver
title: HidRegisterMinidriver function (hidport.h)
description: The HidRegisterMinidriver routine is called by HID minidrivers, during their initialization, to register with the HID class driver.
old-location: hid\hidregisterminidriver.htm
tech.root: hid
ms.assetid: 521928f8-6434-443a-83f0-7e8e00c756b5
ms.date: 04/30/2018
ms.keywords: HidRegisterMinidriver, HidRegisterMinidriver routine [Human Input Devices], hid.hidregisterminidriver, hidfunc_83ef5fb3-46fc-427e-a9de-8aa554ef26b6.xml, hidport/HidRegisterMinidriver
ms.topic: function
req.header: hidport.h
req.include-header: Hidport.h
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
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hid.lib
-	Hid.dll
api_name:
-	HidRegisterMinidriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidRegisterMinidriver function


## -description


The <b>HidRegisterMinidriver</b> routine is called by HID minidrivers, during their initialization, to register with the HID class driver.


## -parameters




### -param MinidriverRegistration [in]

Pointer to a caller-allocated buffer that contains an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff539929">HID_MINIDRIVER_REGISTRATION</a> structure for the minidriver.


## -returns



<b>HidRegisterMinidriver</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the routine completed without error and the minidriver is now registered with the HID class driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that there was insufficient memory for the system to register the minidriver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REVISION_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the HID revision number provided in <i>MinidriverRegistration-&gt;</i>Revision is not supported by this version of the HID class driver.

</td>
</tr>
</table>
 




## -remarks



Before calling this routine, HID minidrivers must initialize all members of the HID_MINIDRIVER_REGISTRATION structure that is provided at <i>MinidriverRegistration</i>. For information about these members, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539929">HID_MINIDRIVER_REGISTRATION</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539929">HID_MINIDRIVER_REGISTRATION</a>
 

 

