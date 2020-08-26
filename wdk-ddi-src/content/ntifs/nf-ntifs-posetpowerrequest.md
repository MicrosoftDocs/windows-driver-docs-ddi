---
UID: NF:ntifs.PoSetPowerRequest
title: PoSetPowerRequest function (ntifs.h)
description: The PoSetPowerRequest routine increments the count for the specified power request type.
old-location: kernel\posetpowerrequest.htm
tech.root: kernel
ms.assetid: 5670a4dd-3804-4532-8765-2fdffe1c4a0b
ms.date: 04/30/2018
keywords: ["PoSetPowerRequest function"]
ms.keywords: PoSetPowerRequest, PoSetPowerRequest routine [Kernel-Mode Driver Architecture], kernel.posetpowerrequest, portn_8f3abb03-a324-4841-b630-b62344d656ce.xml, wdm/PoSetPowerRequest
f1_keywords:
 - "ntifs/PoSetPowerRequest"
 - "PoSetPowerRequest"
req.header: ntifs.h
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoSetPowerRequest
targetos: Windows
req.typenames: 
---

# PoSetPowerRequest function


## -description


The <b>PoSetPowerRequest</b> routine increments the count for the specified power request type.


## -parameters




### -param PowerRequest 
[in, out]
A pointer to a power request object that was created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a> routine.


### -param Type 
[in]
The type of power request. Set this parameter to the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_power_request_type">POWER_REQUEST_TYPE</a> enumeration value:

<ul>
<li>
<b>PowerRequestSystemRequired</b>

</li>
</ul>

## -returns



<b>PoSetPowerRequest</b> returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Type</i> parameter is set to an unsupported value.

</td>
</tr>
</table>
 




## -remarks



A driver can call the <b>PoSetPowerRequest</b> routine to request that the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-manager">power manager</a> override several types of default power behavior, which are specified as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_power_request_type">POWER_REQUEST_TYPE</a> enumeration values. To restore the default behavior, the driver cancels the request by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poclearpowerrequest">PoClearPowerRequest</a> routine.

The power manager maintains a count of the active requests for each power request type. The <b>PoSetPowerRequest</b> routine increments the count for the specified power request type by one. The <b>PoClearPowerRequest</b> routine decrements the count by one. A nonzero count indicates that requests from one or more components are active. After the count decrements to zero, the computer reverts to the default behavior for the specified power request type.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_power_request_type">POWER_REQUEST_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-poclearpowerrequest">PoClearPowerRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a>
 

 

