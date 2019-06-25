---
UID: NF:ntifs.PoClearPowerRequest
title: PoClearPowerRequest function (ntifs.h)
description: The PoClearPowerRequest routine decrements the count for the specified power request type.
old-location: kernel\poclearpowerrequest.htm
tech.root: kernel
ms.assetid: d3754cca-81a4-42d2-a728-9f7e3270a4ee
ms.date: 04/30/2018
ms.keywords: PoClearPowerRequest, PoClearPowerRequest routine [Kernel-Mode Driver Architecture], kernel.poclearpowerrequest, portn_683a4a08-b6e3-4d6c-adfa-00d075db06f9.xml, wdm/PoClearPowerRequest
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoClearPowerRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoClearPowerRequest function


## -description


The <b>PoClearPowerRequest</b> routine decrements the count for the specified power request type.


## -parameters




### -param PowerRequest [in, out]

A pointer to a power request object that was created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a> routine.


### -param Type [in]

The type of the power request. Set this parameter to the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_power_request_type">POWER_REQUEST_TYPE</a> enumeration value:

<ul>
<li><b>PowerRequestSystemRequired</b></li>
</ul>

## -returns



<b>PoClearPowerRequest</b> returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:

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
Parameter <i>Type</i> is set to an unsupported value.

</td>
</tr>
</table>
 




## -remarks



A driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-posetpowerrequest">PoSetPowerRequest</a> routine to request that the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/power-manager">power manager</a> override several types of default power behavior, which are specified as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_power_request_type">POWER_REQUEST_TYPE</a> enumeration values. To restore the default behavior, the driver cancels the request by calling the <b>PoClearPowerRequest</b> routine.

The power manager maintains a count of the active requests for each power request type. The <b>PoSetPowerRequest</b> routine increments the count for the specified power request type by one. The <b>PoClearPowerRequest</b> routine decrements the count by one. A nonzero count indicates that requests from one or more components are active. After the count decrements to zero, the power manager restores the default behavior for the specified power request type. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_power_request_type">POWER_REQUEST_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-pocreatepowerrequest">PoCreatePowerRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-posetpowerrequest">PoSetPowerRequest</a>
 

 

