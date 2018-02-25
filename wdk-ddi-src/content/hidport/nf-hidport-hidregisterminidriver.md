---
UID: NF:hidport.HidRegisterMinidriver
title: HidRegisterMinidriver function
author: windows-driver-content
description: The HidRegisterMinidriver routine is called by HID minidrivers, during their initialization, to register with the HID class driver.
old-location: hid\hidregisterminidriver.htm
old-project: hid
ms.assetid: 521928f8-6434-443a-83f0-7e8e00c756b5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , H, HidRegisterMinidriver, HidRegisterMinidriver routine [Human Input Devices], M, R, d, e, g, hid.hidregisterminidriver, hidfunc_83ef5fb3-46fc-427e-a9de-8aa554ef26b6.xml, hidport/HidRegisterMinidriver, i, n, r, s, t, v"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hid.lib
-	Hid.dll
apiname:
-	HidRegisterMinidriver
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# HidRegisterMinidriver function


## -description


The <b>HidRegisterMinidriver</b> routine is called by HID minidrivers, during their initialization, to register with the HID class driver.


## -syntax


````
NTSTATUS HidRegisterMinidriver(
  _In_ PHID_MINIDRIVER_REGISTRATION MinidriverRegistration
);
````


## -parameters




### -param MinidriverRegistration [in]

Pointer to a caller-allocated buffer that contains an initialized <a href="..\hidport\ns-hidport-_hid_minidriver_registration.md">HID_MINIDRIVER_REGISTRATION</a> structure for the minidriver.


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



Before calling this routine, HID minidrivers must initialize all members of the HID_MINIDRIVER_REGISTRATION structure that is provided at <i>MinidriverRegistration</i>. For information about these members, see <a href="..\hidport\ns-hidport-_hid_minidriver_registration.md">HID_MINIDRIVER_REGISTRATION</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also

<a href="..\hidport\ns-hidport-_hid_minidriver_registration.md">HID_MINIDRIVER_REGISTRATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidRegisterMinidriver routine%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

