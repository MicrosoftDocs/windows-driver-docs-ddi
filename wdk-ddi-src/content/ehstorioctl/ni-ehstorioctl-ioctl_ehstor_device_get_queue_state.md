---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
title: IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE (ehstorioctl.h)
description: The IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE request is sent by silo drivers and applications to determine the state of a storage device queue.
old-location: storage\ioctl_ehstor_device_get_queue_state.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE IOCTL"]
ms.keywords: IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE, IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE control, IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE, storage.ioctl_ehstor_device_get_queue_state
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
 - ehstorioctl/IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE
---

# IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE IOCTL


## -description

The <b>IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE</b> request is sent by silo drivers and applications to determine the state of a storage device queue. IO requests in the storage device queue are held when the device is temporarily unauthorized. A storage device may become temporarily unauthorized in low power states or when there is a policy that requires locking Enhanced Storage devices such as when the user session is locked.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains an <b> ACT_QUEUE_STATE</b>  structure. <b>ACT_QUEUE_STATE</b> is declared in <i>ehstorioctl.h</i> as the following.


```
typedef struct tagACT_QUEUE_STATE
{
    BOOLEAN fFrozen;
} ACT_QUEUE_STATE;
```


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

## -fFrozen

The freeze state of the IO request queue for a storage device. If set to TRUE, the queue is frozen and all IO requests sent to the storage device are held. Otherwise, IO requests in the device queue are processed.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_device_set_queue_state">IOCTL_EHSTOR_DEVICE_SET_QUEUE_STATE</a>
