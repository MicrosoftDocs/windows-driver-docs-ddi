---
UID: NF:wdm.PoCreatePowerRequest
title: PoCreatePowerRequest function
description: The PoCreatePowerRequest routine creates a power request object.
old-location: kernel\pocreatepowerrequest.htm
tech.root: kernel
ms.assetid: 67986bf8-b070-44e9-95a2-eea35100b0e7
ms.date: 04/30/2018
ms.keywords: PoCreatePowerRequest, PoCreatePowerRequest routine [Kernel-Mode Driver Architecture], kernel.pocreatepowerrequest, portn_059f00e2-74ea-4c61-8fcd-6b257c084161.xml, wdm/PoCreatePowerRequest
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoCreatePowerRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoCreatePowerRequest function


## -description


The <b>PoCreatePowerRequest</b> routine creates a power request object.


## -parameters




### -param PowerRequest [out]

A pointer to a location into which the routine writes a pointer to the newly created power request object. If the call fails, the routine writes <b>NULL</b> to this location.


### -param DeviceObject [in]

A pointer to the device object of the caller (a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure).


### -param Context [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542081">COUNTED_REASON_CONTEXT</a> structure that describes why the caller is creating the power request object. This parameter is optional and can be set to <b>NULL</b>.


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



This routine creates a power request object. To enable power requests, the caller should create one power request object and use that object for all calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559762">PoSetPowerRequest</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559658">PoClearPowerRequest</a> routines.

A driver can use power requests to override certain aspects of the computer's default power behavior. For example, a driver for a TV receiver device can use power requests to prevent the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> from automatically blanking the display during extended periods of time in which no user interaction occurs.

When the power request object is no longer needed, the caller must delete the object by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559665">PoDeletePowerRequest</a> routine. The driver must delete the power request object before it deletes the device object that was used to create the power request object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559658">PoClearPowerRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559665">PoDeletePowerRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559762">PoSetPowerRequest</a>
 

 

