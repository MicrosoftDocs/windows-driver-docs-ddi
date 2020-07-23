---
UID: NI:nfpdev.IOCTL_NFP_DISABLE
title: IOCTL_NFP_DISABLE (nfpdev.h)
description: A client sends the IOCTL_NFP_DISABLE request to temporarily disable subscriptions, publications, and presence events.
old-location: nfpdrivers\ioctl_nfp_disable.htm
tech.root: nfpdrivers
ms.assetid: 5999EBAE-9B4A-469C-A8CE-E0A72B6F6A14
ms.date: 02/15/2018
keywords: ["IOCTL_NFP_DISABLE IOCTL"]
ms.keywords: IOCTL_NFP_DISABLE, IOCTL_NFP_DISABLE control, IOCTL_NFP_DISABLE control code [Near-Field Proximity Drivers], nfpdev/IOCTL_NFP_DISABLE, nfpdrivers.ioctl_nfp_disable
f1_keywords:
 - "nfpdev/IOCTL_NFP_DISABLE"
 - "IOCTL_NFP_DISABLE"
req.header: nfpdev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
- nfpdev.h
api_name:
- IOCTL_NFP_DISABLE
targetos: Windows
req.typenames: 
---

# IOCTL_NFP_DISABLE IOCTL


## -description


A client sends the <b>IOCTL_NFP_DISABLE</b> request to temporarily disable subscriptions, publications, and presence events. This is useful when a client wants to disable the proximity functionality but keep the resources allocated to quickly re-enable them when needed again.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



The following are required actions when using this IOCTL:<ul>
<li>
	When this IOCTL is received the driver MUST mark the file handle as “Disabled”.

</li>
<li>
If a subscription handle is changed to “Disabled, the provider MUST remove all messages from that file handle’s “Received” queue.

</li>
<li>
If a subscription handle is “Disabled”:

<ul>
<li>
The driver MUST keep that handle’s “Received” queue at zero length by purging (dropping) existing messages in the queue and by dropping new messages from the queue as soon as they are received.

</li>
<li>
The driver MUST complete all pended <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfpdev/ni-nfpdev-ioctl_nfp_get_next_subscribed_message">IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE</a>  requests on that handle with STATUS_CANCELLED.

</li>
</ul>
</li>
<li>
	If a publication handle is “Disabled”, the provider MUST NOT transmit the publication’s message and it MUST complete all pended <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfpdev/ni-nfpdev-ioctl_nfp_get_next_transmitted_message">IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE</a> requests on that handle with STATUS_CANCELLED

</li>
</ul>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfpdev/ni-nfpdev-ioctl_nfp_enable">IOCTL_NFP_ENABLE</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a>
 

 

