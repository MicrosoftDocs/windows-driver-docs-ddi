---
UID: NI:avc.IOCTL_AVC_BUS_RESET
title: IOCTL_AVC_BUS_RESET
author: windows-driver-content
description: The IOCTL_AVC_BUS_RESET I/O control code allows the caller to complete any previous IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO and IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO control requests that did not use the AVC_SUBUNIT_ADDR_TRIGGERBUSRESET flag.
old-location: stream\ioctl_avc_bus_reset.htm
old-project: stream
ms.assetid: 8f87ee5f-74bb-446f-8be3-214cc2c01c1b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_AVC_BUS_RESET, IOCTL_AVC_BUS_RESET control code [Streaming Media Devices], avc/IOCTL_AVC_BUS_RESET, avcref_4be76d4b-17fe-4ae6-a078-ebb079499d55.xml, stream.ioctl_avc_bus_reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: avc.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avc.h
api_name:
-	IOCTL_AVC_BUS_RESET
product: Windows
targetos: Windows
req.typenames: AVC_FUNCTION
---

# IOCTL_AVC_BUS_RESET IOCTL


## -description



The IOCTL_AVC_BUS_RESET I/O control code allows the caller to complete any previous IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO and IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO control requests that did not use the AVC_SUBUNIT_ADDR_TRIGGERBUSRESET flag. It is available to user mode as well as kernel-mode components through the IRP_MJ_DEVICE_CONTROL dispatch. 

For driver-to-driver communication, it is a METHOD_BUFFERED IOCTL, so set the IRP fields accordingly (IrpStack-&gt;Parameters.DeviceIoControl.InputBufferLength and Irp-&gt;AssociatedIrp.SystemBuffer). This request does not require any additional parameters, so the input and output buffers should be set to <b>NULL</b>.

This request causes <i>avc.sys</i> to invalidate its device relations, which results in the PnP manager asking for an updated list of child device objects (virtual subunits). If there are no new or removed child device objects, no action will be taken. If there are new or removed child device objects, their drivers will be loaded or unloaded, and a 1394 bus reset will be triggered for each PDO as each is started or removed.




## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



Must be called at IRQL = PASSIVE_LEVEL




## -see-also

<a href="..\avc\ni-avc-ioctl_avc_remove_virtual_subunit_info.md">IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO</a>



<a href="..\avc\ns-avc-_avc_subunit_addr_spec.md">AVC_SUBUNIT_ADDR_SPEC</a>



<a href="..\avc\ni-avc-ioctl_avc_class.md">IOCTL_AVC_CLASS</a>



<a href="..\avc\ni-avc-ioctl_avc_update_virtual_subunit_info.md">IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO</a>



 

 


