---
UID: NC:storport.HW_BUILDIO
title: HW_BUILDIO
author: windows-driver-content
description: The HwStorBuildIo routine processes the SRB with unsynchronized access to shared system data structures before passing it to HwStorStartIo.
old-location: storage\hwstorbuildio.htm
old-project: storage
ms.assetid: ebbb8289-5996-4d99-98b6-e95fd9dc7ec9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstorbuildio, HwStorBuildIo routine [Storage Devices], HwStorBuildIo, HW_BUILDIO, HW_BUILDIO, storport/HwStorBuildIo, stormini_3411fed2-32e6-4a3a-a9c3-0bbe0bb514ca.xml
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
-	HwStorBuildIo
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_BUILDIO callback


## -description


The <b>HwStorBuildIo</b> routine processes the SRB with unsynchronized access to shared system data structures before passing it to <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>.


## -prototype


````
HW_BUILDIO HwStorBuildIo;

BOOLEAN HwStorBuildIo(
   IN PVOID               DeviceExtension,
   IN PSCSI_REQUEST_BLOCK Srb 
)
{ ... }
````


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per HBA storage area. 


### -param Srb

A pointer to the SCSI request block (SRB) to be processed.


## -returns


<b>HwStorBuildIo</b> returns <b>TRUE</b> to inform the caller that StorPort should call the <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> routine if StorPort considers the LUN ready to receive I/O. <b>HwStorBuildIo</b> returns <b>FALSE</b> to inform the caller that the SRB should not be passed to <b>HwStorStartIo</b>. In such cases, the miniport driver must complete the SRB by calling <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> with a notification type of <b>RequestComplete</b>. This can be done in <b>HwStorBuildIo</b> or elsewhere in the miniport driver, as long as the SRB is completed before the timeout that is specified in the <b>TimeOutValue</b> field of the SRB structure.



## -remarks


The name <b>HwStorBuildIo</b> is just a placeholder for the miniport function that is pointed to by the <b>HwBuildIo</b> member in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. The actual prototype of this routine is defined in Storport.h as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
HW_BUILDIO (
  _In_ PVOID DeviceExtension,
  _In_ PSCSI_REQUEST_BLOCK  Srb
  );</pre>
</td>
</tr>
</table></span></div>The port driver calls the <b>HwStorBuildIo</b> routine at DISPATCH IRQL without holding any spin locks. Because of this, memory allocation using <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a> and mutual exclusion via <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a> are allowed in <b>HwStorBuildIo</b>. In a multiprocessor environment, more than one <b>HwStorBuildIo</b> can be active at a time, so the miniport driver is required to synchronize access to system resources, which may be in contention if more than one instance of  <b>HwStorBuildIo</b> is active at any given time.

By completed time-consuming I/O setup activities in <b>HwStorBuildIo</b> instead of in <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>, the miniport driver enables greater I/O concurrency and therefore improves I/O throughput. For highest performance, miniport drivers are expected to do as much preprocessing as possible in <b>HwStorBuildIo</b> so that it can send requests to the HBA via <b>HwStorStartIo</b> in as short amount of time as possible. Preprocessed data and state can be stored in either the <i>DeviceExtension</i> or <i>SrbExtension</i> structures. Only modifications to unique portions of the <i>DeviceExtension</i> must occur since no locks are held. <b>HwStorBuildIo</b> and <b>HwStorStartIo</b> receive the following Srb function types:
<table>
<tr>
<th>Srb function</th>
<th>Expected action</th>
<th>Remarks</th>
</tr>
<tr>
<td>
SRB_FUNCTION_EXECUTE_SCSI 

</td>
<td>
Sends a CDB to the specified bus/target/lun.

</td>
<td>
Srb-&gt;DataTransferLength is valid for all Cdbs. 

Srb-&gt;DataBuffer is <b>NULL</b> for read and write requests . To access the associated data, either use <a href="..\storport\nf-storport-storportgetscattergatherlist.md">StorPortGetScatterGatherList</a> (for Dma transfers) or <a href="..\storport\nf-storport-storportgetsystemaddress.md">StorPortGetSystemAddress</a> (for program controlled I/O ) to get the Scatter Gather list or the virtual address of the buffer.

For other requests, Srb-&gt;Databuffer points to the data that is associated with the Srb.

Srb-&gt;PathId is valid and represents the pathid given to Storport in <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> (BusChange). Writers of miniport drivers need to use pathid as an index into a table of busses within the miniport. 

 Srb-&gt;TargetId and Srb-&gt;Lun are valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_IO_CONTROL 

</td>
<td>
Miniport defined.

</td>
<td>
Srb-&gt;DataTransferLength and Srb-&gt;DataBuffer are valid if set by the requester.

Srb-&gt;PathId, Srb-&gt;TargetId, and Srb-&gt;Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_RESET_LOGICAL_UNIT

</td>
<td>
Reset the specified logical unit (if the device is capable).

</td>
<td>
Srb-&gt;DataTransferLength and Srb-&gt;DataBuffer are invalid.

Srb-&gt;PathId, Srb-&gt;TargetId, and Srb-&gt;Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_RESET_DEVICE 

</td>
<td>
Reset the specified Scsi Target.

</td>
<td>
Srb-&gt;DataTransferLength and Srb-&gt;DataBuffer, Srb-&gt;Lun are invalid.

Srb-&gt;PathId and Srb-&gt;TargetId are valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_RESET_BUS 

</td>
<td>
Reset all of the targets on the specified SCSI bus.

</td>
<td>
Only Srb-&gt;PathId is valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_FLUSH 

</td>
<td>
Only performed by the miniport driver if it sets <b>CachesData</b> == <b>TRUE</b> in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. Instructs the miniport driver to flush all cached data.

</td>
<td>
Srb-&gt;PathId, Srb-&gt;TargetId, and Srb-&gt;Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_SHUTDOWN

</td>
<td>
Only performed by the miniport driver if it sets <b>CachesData</b> == <b>TRUE</b> in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. Instructs the miniport driver to flush all cached data preparatory to shut down.

</td>
<td>
Srb-&gt;PathId, Srb-&gt;TargetId, and Srb-&gt;Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_DUMP_POINTERS

</td>
<td>
This request is sent to a Storport virtual miniport driver that is used to control the disk that holds the crash dump data. The request supplies information needed for the miniport driver to support crash dump and hibernation.

Starting with Windows 8, non-virtual miniport drivers can optionally receive this request

</td>
<td>
Srb-&gt;PathId, Srb-&gt;TargetId, and Srb-&gt;Lun are all valid.

</td>
</tr>
<tr>
<td>
SRB_FUNCTION_FREE_DUMP_POINTERS

</td>
<td>
Starting with Windows 8, this request is sent to the miniport to free and resources allocated during the SRB_FUNCTION_DUMP_POINTERS request.

</td>
<td>
Srb-&gt;PathId, Srb-&gt;TargetId, and Srb-&gt;Lun are all valid.

</td>
</tr>
</table> 

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> or <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

For more information about what you can and cannot do safely in this miniport driver routine, see <a href="https://msdn.microsoft.com/6b18e3ff-30dd-414b-99b5-4bb914660a67">Unsynchronized HwStorBuildIo Routine</a>. 



## -see-also

<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>

<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>

<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>

<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>

<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>

<a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>

<a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_BUILDIO routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

