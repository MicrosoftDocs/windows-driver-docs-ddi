---
UID: NI:bthioctl.IOCTL_BTH_DISCONNECT_DEVICE
title: IOCTL_BTH_DISCONNECT_DEVICE
author: windows-driver-content
description: Profile drivers use IOCTL_BTH_DISCONNECT_DEVICE to request the operating system to disconnect the specified remote device.
old-location: bltooth\ioctl_bth_disconnect_device.htm
old-project: bltooth
ms.assetid: 03c7f389-60a4-4c98-881d-a58926644275
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.ioctl_bth_disconnect_device, IOCTL_BTH_DISCONNECT_DEVICE control code [Bluetooth Devices], IOCTL_BTH_DISCONNECT_DEVICE, bthioctl/IOCTL_BTH_DISCONNECT_DEVICE, bth_ioctls_03f58c9a-06b9-45b9-b817-3ef86058af5e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthioctl.h
apiname:
-	IOCTL_BTH_DISCONNECT_DEVICE
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_DISCONNECT_DEVICE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Profile drivers use IOCTL_BTH_DISCONNECT_DEVICE to request the operating system to disconnect the
     specified remote device.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains the address of the remote device to disconnect
      from.


### -input-buffer-length

The length of the address in the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to zero because the Bluetooth driver
      stack returns no data with this IOCTL.

The 
      <b>Status</b> member is set to one of the values in the following table.
<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
<td>
The specified remote device is not connected.

</td>
</tr>
</table> 


## -remarks


Calling IOCTL_BTH_DISCONNECT_DEVICE forces a disconnect from the remote device without regard to the
    state of any L2CAP and SCO connections. All active SCO connections will be disconnected before the ACL
    connection is disconnected. Pending data transfers might fail.


