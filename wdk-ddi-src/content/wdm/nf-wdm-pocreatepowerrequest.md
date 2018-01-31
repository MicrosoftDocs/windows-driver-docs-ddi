---
UID: NF:wdm.PoCreatePowerRequest
title: PoCreatePowerRequest function
author: windows-driver-content
description: The PoCreatePowerRequest routine creates a power request object.
old-location: kernel\pocreatepowerrequest.htm
old-project: kernel
ms.assetid: 67986bf8-b070-44e9-95a2-eea35100b0e7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoCreatePowerRequest routine [Kernel-Mode Driver Architecture], wdm/PoCreatePowerRequest, PoCreatePowerRequest, portn_059f00e2-74ea-4c61-8fcd-6b257c084161.xml, kernel.pocreatepowerrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PoCreatePowerRequest
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoCreatePowerRequest function


## -description


The <b>PoCreatePowerRequest</b> routine creates a power request object.


## -syntax


````
NTSTATUS PoCreatePowerRequest(
  _Out_ PVOID                   *PowerRequest,
  _In_  PDEVICE_OBJECT          DeviceObject,
  _In_  PCOUNTED_REASON_CONTEXT Context
);
````


## -parameters




#### - PowerRequest [out]

A pointer to a location into which the routine writes a pointer to the newly created power request object. If the call fails, the routine writes <b>NULL</b> to this location.


#### - DeviceObject [in]

A pointer to the device object of the caller (a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure).


#### - Context [in]

A pointer to a <a href="..\wdm\ns-wdm-_counted_reason_context.md">COUNTED_REASON_CONTEXT</a> structure that describes why the caller is creating the power request object. This parameter is optional and can be set to <b>NULL</b>.


## -returns


<b>PoCreatePowerRequest</b> returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>DeviceObject</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is not enough memory available to create a power request object.

</td>
</tr>
</table> 



## -remarks


This routine creates a power request object. To enable power requests, the caller should create one power request object and use that object for all calls to the <a href="..\wdm\nf-wdm-posetpowerrequest.md">PoSetPowerRequest</a> and <a href="..\wdm\nf-wdm-poclearpowerrequest.md">PoClearPowerRequest</a> routines.

A driver can use power requests to override certain aspects of the computer's default power behavior. For example, a driver for a TV receiver device can use power requests to prevent the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> from automatically blanking the display during extended periods of time in which no user interaction occurs.

When the power request object is no longer needed, the caller must delete the object by calling the <a href="..\wdm\nf-wdm-podeletepowerrequest.md">PoDeletePowerRequest</a> routine. The driver must delete the power request object before it deletes the device object that was used to create the power request object.



## -see-also

<a href="..\wdm\nf-wdm-posetpowerrequest.md">PoSetPowerRequest</a>

<a href="..\wdm\nf-wdm-podeletepowerrequest.md">PoDeletePowerRequest</a>

<a href="..\wdm\nf-wdm-poclearpowerrequest.md">PoClearPowerRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoCreatePowerRequest routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

