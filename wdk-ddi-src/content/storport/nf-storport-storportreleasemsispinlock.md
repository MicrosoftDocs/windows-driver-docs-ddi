---
UID: NF:storport.StorPortReleaseMSISpinLock
title: StorPortReleaseMSISpinLock function (storport.h)
description: The StorPortReleaseMSISpinLock routine releases a previously acquired message signaled interrupt (MSI) spin lock for the specified message.
old-location: storage\storportreleasemsispinlock.htm
tech.root: storage
ms.assetid: 5a2cf757-9dca-4717-a775-834a22c02a12
ms.date: 03/29/2018
keywords: ["StorPortReleaseMSISpinLock function"]
ms.keywords: StorPortReleaseMSISpinLock, StorPortReleaseMSISpinLock routine [Storage Devices], storage.storportreleasemsispinlock, storport/StorPortReleaseMSISpinLock, storprt_212b8090-c4a3-4ea8-8c50-6704a6d0cee7.xml
f1_keywords:
 - "storport/StorPortReleaseMSISpinLock"
 - "StorPortReleaseMSISpinLock"
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
- StorPortReleaseMSISpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReleaseMSISpinLock function


## -description


The <b>StorPortReleaseMSISpinLock</b> routine releases a previously acquired message signaled interrupt (MSI) spin lock for the specified message. 


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param MessageId

<p>The identifier of the message.</p>


### -param OldIrql [in]

The IRQL that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquiremsispinlock">StorPortAcquireMSISpinLock</a> routine returned when the miniport driver acquired the spin lock.


## -returns



StorPortReleaseMSISpinLock returns one of the following status codes:

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
Indicates that the spin lock was released successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
HwDeviceExtension was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



Miniport drivers are not required to acquire MSI spin locks for messages unless the <b>InterruptSynchronizePerMessage</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structure indicates a synchronization mode of <b>InterruptSynchronizationMode</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquiremsispinlock">StorPortAcquireMSISpinLock</a>
 

 

