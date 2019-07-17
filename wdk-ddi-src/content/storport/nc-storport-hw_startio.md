---
UID: NC:storport.HW_STARTIO
title: HW_STARTIO (storport.h)
description: The Storport driver calls the HwStorStartIo routine one time for each incoming I/O request.
old-location: storage\hwstorstartio.htm
tech.root: storage
ms.assetid: 73085ca7-a442-4c16-b1e3-6de048e7f1f7
ms.date: 03/29/2018
ms.keywords: HW_STARTIO, HwStorStartIo, HwStorStartIo routine [Storage Devices], storage.hwstorstartio, stormini_8f910467-49f3-4f15-919d-84edee8ad053.xml, storport/HwStorStartIo
ms.topic: callback
f1_keywords:
 - "storport/HwStorStartIo"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Storport.h
api_name:
- HwStorStartIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_STARTIO callback function


## -description


The Storport driver calls the <b>HwStorStartIo</b> routine one time for each incoming I/O request.


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area.


### -param Srb

A pointer to the SCSI request block to be started. 


## -returns



<b>HwStorStartIo</b> returns <b>TRUE</b> if the request was successfully initiated. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>HwStorStartIo</b> initiates an I/O operation. StorPort is designed to use miniport private data that is prepared in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_buildio">HwStorBuildIo</a> and stored in either the <i>DeviceExtension</i> or <i>Srb->SrbExtension</i>.  Because <b>HwStorBuildIo</b> is called without spin locks, the best driver performance is achieved by preparing as much data  as possible in <b>HwStorBuildIo</b>.

Storport calls <b>HwStorStartIo</b> in the following ways:

<ul>
<li>
For <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/overview-of-storage-virtual-miniport-drivers">storage non-virtual miniport drivers</a>, depending on the value of <b>SynchronizationModel</b> set in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a>, Storport always calls <b>HwStorStartIo</b> the same IRQL and uses an internal spin lock to ensure that I/O requests are initiated sequentially.  The IRQL is either DISPATCH_LEVEL (full-duplex mode) or DIRQL (half-duplex mode).

When handling I/O in  half-duplex mode, the <b>HwStorStartIo</b> routine does not have to acquire its own spin lock. Also, memory allocation using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportallocatepool">StorPortAllocatePool</a> and mutual exclusion via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a> are not allowed in the <b>HwStorStartIo</b> routine. In full-duplex mode, <b>StorPortAllocatePool</b> and <b>StorPortAcquireSpinLock</b> may be used in the <b>HwStorStartIo</b> routine.

If a non-virtual miniport supports the concurrent channels optimization (STOR_PERF_CONCURRENT_CHANNELS set by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitializeperfopts">StorPortInitializePerfOpts</a>), multiple calls to <b>HwStorStartIo</b> concurrently are possible. In this case, the miniport will need to ensure that any shared resources are protected by a lock. With this performance optimization, Storport will not acquire the StartIo lock prior to calling <b>HwStorStartIo</b> and the miniport must provide its own lock if required.

</li>
<li>
For <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storage-virtual-miniport-drivers">storage virtual miniport drivers</a>, Storport calls <b>HwStorStartIo</b> at any IRQL <= DISPATCH_LEVEL and does not use an internal spin lock. The <b>HwStorStartIo</b> routine may acquire its own spin lock by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>. Also, calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportallocatepool">StorPortAllocatePool</a>  are allowed in the <b>HwStorStartIo</b> routine of a storage virtual miniport driver.

</li>
</ul>
The SRB is expected to be completed when SCSI status is received. When the Storport driver completes the SRB by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportnotification">StorPortNotification</a> with a <i>NotificationType</i> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportnotification">RequestComplete</a>, an SRB is expected to return one of the following values in the <b>SrbStatus</b> field of the Srb:

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
None, except to complete the request by using  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportnotification">StorPortNotification for RequestComplete</a>,  probably from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_dpc_routine">HwStorDpcRoutine</a>.

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
 

The name <b>HwStorStartIo</b> is a placeholder to describe the miniport routine set in the <b>HwStartIo</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure. This structure is passed in the <i>HwInitializationData</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The actual prototype of this routine is defined in Storport.h as follows:

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
</table></span></div>
Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.


#### Examples

To define a <b>HwStorStartIo</b> callback routine, you must first provide a function declaration that <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as shown in the following code example:

To define an <b>HwStorStartIo</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorStartIo</b> callback routine that is named <i>MyHwStartIo</i>, use the <b>HW_STARTIO</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_STARTIO MyHwStartIo;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
MyHwStartIo (
  _In_ PVOID  DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_STARTIO</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_STARTIO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_buildio">HwStorBuildIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitialize">StorPortInitialize</a>
 

 

