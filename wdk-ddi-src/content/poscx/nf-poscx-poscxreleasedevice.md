---
UID: NF:poscx.PosCxReleaseDevice
title: PosCxReleaseDevice function
author: windows-driver-content
description: PosCxReleaseDevice is called to release a device that was previously claimed with PosCxClaimDevice. Once the device is released, the next pending claim requester is promoted.
old-location: pos\poscxreleasedevice.htm
old-project: pos
ms.assetid: 9615915C-B729-4702-BF41-D5068B43A729
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxReleaseDevice, PosCxReleaseDevice function, pos.poscxreleasedevice, poscx/PosCxReleaseDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	PosCxReleaseDevice
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxReleaseDevice function


## -description


      PosCxReleaseDevice is called to release a device that was previously claimed with
      <a href="..\poscx\nf-poscx-poscxclaimdevice.md">PosCxClaimDevice</a>.
      Once the device is released, the next pending claim requester is promoted.


## -syntax


````
NTSTATUS PosCxReleaseDevice(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

      A handle to a framework file object that identifies the caller.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The device was successfully released.</td>
</tr>
<tr>
<td><b>STATUS_ACCESS_DENIED</b></td>
<td>The calling thread is not the owner of the device.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER </b></td>
<td>The specified <i>fileObject</i> is invalid.</td>
</tr>
</table>
 




## -see-also

<a href="..\poscx\nf-poscx-poscxclaimdevice.md">PosCxClaimDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxReleaseDevice function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

