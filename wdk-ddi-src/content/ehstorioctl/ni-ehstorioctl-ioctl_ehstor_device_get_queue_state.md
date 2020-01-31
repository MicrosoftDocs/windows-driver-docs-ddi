---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
title: IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE (ehstorioctl.h)
description: The IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE request is sent by silo drivers and applications to determine the state of a storage device queue.
old-location: storage\ioctl_ehstor_device_get_queue_state.htm
tech.root: storage
ms.assetid: 1BF7E7B3-26CF-41BB-B2E9-8EDC6872CF34
ms.date: 03/29/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE, IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE control, IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE, storage.ioctl_ehstor_device_get_queue_state
f1_keywords:
 - "ehstorioctl/IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE"
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- EhStorIoctl.h
api_name:
- IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE IOCTL


## -description


The <b>IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE</b> request is sent by silo drivers and applications to determine the state of a storage device queue. IO requests in the storage device queue are held when the device is temporarily unauthorized. A storage device may become temporarily unauthorized in low power states or when there is a policy that requires locking Enhanced Storage devices such as when the user session is locked.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains an <b> ACT_QUEUE_STATE</b>  structure. <b>ACT_QUEUE_STATE</b> is declared in <i>ehstorioctl.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct tagACT_QUEUE_STATE
{
    BOOLEAN fFrozen;
} ACT_QUEUE_STATE;</pre>
</td>
</tr>
</table></span></div>



#### -fFrozen

The freeze state of the IO request queue for a storage device. If set to TRUE, the queue is frozen and all IO requests sent to the storage device are held. Otherwise, IO requests in the device queue are processed.


### -output-buffer-length

The length of an <b> ACT_QUEUE_STATE</b>  structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The queue state was returned successfully.</td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>The output buffer length is too small.</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_device_set_queue_state">IOCTL_EHSTOR_DEVICE_SET_QUEUE_STATE</a>
 

 

