---
UID: NC:storport.HW_STARTIO
title: HW_STARTIO
author: windows-driver-content
description: The Storport driver calls the HwStorStartIo routine one time for each incoming I/O request.
old-location: storage\hwstorstartio.htm
old-project: storage
ms.assetid: 73085ca7-a442-4c16-b1e3-6de048e7f1f7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstorstartio, HwStorStartIo routine [Storage Devices], HwStorStartIo, HW_STARTIO, HW_STARTIO, storport/HwStorStartIo, stormini_8f910467-49f3-4f15-919d-84edee8ad053.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks section.)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorStartIo
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_STARTIO callback


## -description


The Storport driver calls the <b>HwStorStartIo</b> routine one time for each incoming I/O request.


## -prototype


````
HW_STARTIO HwStorStartIo;

BOOLEAN HwStorStartIo(
   IN PVOID               DeviceExtension,
   IN PSCSI_REQUEST_BLOCK Srb
)
{ ... }
````


## -parameters




#### - DeviceExtension

A pointer to the miniport driver's per HBA storage area.


#### - Srb

A pointer to the SCSI request block to be started. 


## -returns


<b>HwStorStartIo</b> returns <b>TRUE</b> if the request was successfully initiated. Otherwise, it returns <b>FALSE</b>. 



## -remarks


<b>HwStorStartIo</b> initiates an I/O operation. StorPort is designed to use miniport private data that is prepared in <a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a> and stored in either the <i>DeviceExtension</i> or <i>Srb-&gt;SrbExtension</i>.  Because <b>HwStorBuildIo</b> is called without spin locks, the best driver performance is achieved by preparing as much data  as possible in <b>HwStorBuildIo</b>.

Storport calls <b>HwStorStartIo</b> in the following ways:
<ul>
<li>
For <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/storage/overview-of-storage-virtual-miniport-drivers">storage non-virtual miniport drivers</a>, depending on the value of <b>SynchronizationModel</b> set in <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>, Storport always calls <b>HwStorStartIo</b> the same IRQL and uses an internal spin lock to ensure that I/O requests are initiated sequentially.  The IRQL is either DISPATCH_LEVEL (full-duplex mode) or DIRQL (half-duplex mode).

When handling I/O in  half-duplex mode, the <b>HwStorStartIo</b> routine does not have to acquire its own spin lock. Also, memory allocation using <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a> and mutual exclusion via <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a> are not allowed in the <b>HwStorStartIo</b> routine. In full-duplex mode, <b>StorPortAllocatePool</b> and <b>StorPortAcquireSpinLock</b> may be used in the <b>HwStorStartIo</b> routine.

If a non-virtual miniport supports the concurrent channels optimization (STOR_PERF_CONCURRENT_CHANNELS set by <a href="..\storport\nf-storport-storportinitializeperfopts.md">StorPortInitializePerfOpts</a>), multiple calls to <b>HwStorStartIo</b> concurrently are possible. In this case, the miniport will need to ensure that any shared resources are protected by a lock. With this performance optimization, Storport will not acquire the StartIo lock prior to calling <b>HwStorStartIo</b> and the miniport must provide its own lock if required.

</li>
<li>
For <a href="https://msdn.microsoft.com/971558ae-96a3-43a5-94bd-4883bb9feb58">storage virtual miniport drivers</a>, Storport calls <b>HwStorStartIo</b> at any IRQL &lt;= DISPATCH_LEVEL and does not use an internal spin lock. The <b>HwStorStartIo</b> routine may acquire its own spin lock by calling <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>. Also, calls to <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a>  are allowed in the <b>HwStorStartIo</b> routine of a storage virtual miniport driver.

</li>
</ul>The SRB is expected to be completed when SCSI status is received. When the Storport driver completes the SRB by calling <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> with a <i>NotificationType</i> of <a href="https://msdn.microsoft.com/abceaf2c-3512-409c-9274-096eab810ab2">RequestComplete</a>, an SRB is expected to return one of the following values in the <b>SrbStatus</b> field of the Srb:
<table>
<tr>
<th>Status</th>
<th>Indicates</th>
<th>StorPort Action</th>
<th>Miniport action</th>
</tr>
<tr>
<td>
SRB_STATUS_SUCCESS

</td>
<td>
The Srb was sent and SCSI status (possibly with data) was returned.

</td>
<td>
Returns the data and status to the caller.

</td>
<td>
None, except to complete the request by using  <a href="https://msdn.microsoft.com/library/windows/hardware/ff567446">StorPortNotification for RequestComplete</a>,  probably from the <a href="..\storport\nc-storport-hw_dpc_routine.md">HwStorDpcRoutine</a>.

</td>
</tr>
<tr>
<td>
SRB_STATUS_BUSY

</td>
<td>
There is a temporary problem with sending the Srb (for example, adapter registers or buffers are busy).

</td>
<td>
Discards the original Srb and issues a new Srb, including calls to <b>HwStorBuildIo</b> and <b>HwStorStartIo</b>. All data in the SrbExtension will be lost.

</td>
<td>
Because a new SRB is issued, the miniport must make sure that it never issues SRB_STATUS_BUSY in the middle of a SCSI transaction. After the transaction is started, it must be completed or canceled.  Hardware busy states during the transaction must be handled by the miniport driver.

</td>
</tr>
</table> 

The name <b>HwStorStartIo</b> is a placeholder to describe the miniport routine set in the <b>HwStartIo</b> member of <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. This structure is passed in the <i>HwInitializationData</i> parameter of <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The actual prototype of this routine is defined in Storport.h as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
(*PHW_STARTIO) (
  _In_ PVOID  DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );</pre>
</td>
</tr>
</table></span></div>Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> or <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.



## -see-also

<a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>

<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>

<a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a>

<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_STARTIO routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

