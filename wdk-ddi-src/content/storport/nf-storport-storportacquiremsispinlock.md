---
UID: NF:storport.StorPortAcquireMSISpinLock
title: StorPortAcquireMSISpinLock function (storport.h)
description: The StorPortAcquireMSISpinLock routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message.
old-location: storage\storportacquiremsispinlock.htm
tech.root: storage
ms.assetid: 8aa5a8a6-2024-4b3e-a500-5a484d937a62
ms.date: 03/29/2018
keywords: ["StorPortAcquireMSISpinLock function"]
ms.keywords: StorPortAcquireMSISpinLock, StorPortAcquireMSISpinLock routine [Storage Devices], storage.storportacquiremsispinlock, storport/StorPortAcquireMSISpinLock, storprt_0db1ab5c-a2a5-4362-84e0-493a5cebc2d3.xml
f1_keywords:
 - "storport/StorPortAcquireMSISpinLock"
 - "StorPortAcquireMSISpinLock"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortAcquireMSISpinLock
targetos: Windows
req.typenames: 
---

# StorPortAcquireMSISpinLock function


## -description


The <b>StorPortAcquireMSISpinLock</b> routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param MessageId

<p>The identifier of the message whose spin lock the caller acquires.</p>


### -param OldIrql [in]

A pointer to the storage for the original IRQL value to be used in a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreleasemsispinlock">StorPortReleaseMSISpinLock</a>.


## -returns



<b>StorPortAcquireMSISpinLock</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the spin lock was acquired successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



A miniport driver calls the <b>StorPortAcquireMSISpinLock</b> routine to acquire the MSI spin lock for a particular message. To release the spin lock, the miniport driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreleasemsispinlock">StorPortReleaseMSISpinLock</a> routine. This routine is used by a miniport drivers to acquire a  the MSI spin lock for an individual message only when the <b>InterruptSynchronizationMode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structure is set to <b>InterruptSynchronizePerMessage</b>.

When a miniport needs to synchronize with all messages, it can use one call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a> which will acquire a lock for each message in the proper order.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreleasemsispinlock">StorPortReleaseMSISpinLock</a>
 

 

