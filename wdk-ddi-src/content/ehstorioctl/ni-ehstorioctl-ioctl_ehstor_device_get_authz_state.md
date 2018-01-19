---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_GET_AUTHZ_STATE
title: IOCTL_EHSTOR_DEVICE_GET_AUTHZ_STATE
author: windows-driver-content
description: This IOCTL is used to inform the owning driver for the IEEE 1667 device PDOs that the authorization state has changed.
old-location: storage\ioctl_ehstor_device_get_authz_state.htm
old-project: storage
ms.assetid: 20322156-316B-4FE5-A804-14506C8CEB49
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PDO_TYPE, PDO_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_DEVICE_GET_AUTHZ_STATE
req.alt-loc: EhStorIoctl.h
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
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DEVICE_GET_AUTHZ_STATE IOCTL



## -description
This IOCTL is used to inform the owning driver for the IEEE 1667 device PDOs that the authorization state has changed. The owning driver may choose to change the state of the disk PDO in response to this IOCTL. In the case of <i> EhStorClass.sys</i>, the disk PDO is added or removed based on the authorization value in the input buffer of this IOCTL. Typically this IOCTL is issued by a UMDF authentication silo driver, such as the password or certificate driver, immediately following a successful silo operation which has changed the authentication state of the silo.



## -ioctlparameters

### -input-buffer
The input buffer at Irp-&gt;AssociatedIrp.SystemBuffer must contain a structure of type <a href="..\ehstorioctl\ns-ehstorioctl-tagact_authz_state.md">ACT_AUTHZ_STATE</a>.


### -input-buffer-length
The length of an <a href="..\ehstorioctl\ns-ehstorioctl-tagact_authz_state.md">ACT_AUTHZ_STATE</a> structure.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The authorization state for the ACT was successfully set according to the data contained in the input buffer.

</dd>
</dl>


STATUS_SUCCESS - The authorization state for the ACT was successfully set according to the data contained in the input buffer.


<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.

</dd>
</dl>


STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.


## -remarks
