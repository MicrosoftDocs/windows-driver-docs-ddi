---
UID: NI:nfpdev.IOCTL_NFP_DISABLE
title: IOCTL_NFP_DISABLE
author: windows-driver-content
description: A client sends the IOCTL_NFP_DISABLE request to temporarily disable subscriptions, publications, and presence events.
old-location: nfpdrivers\ioctl_nfp_disable.htm
old-project: nfpdrivers
ms.assetid: 5999EBAE-9B4A-469C-A8CE-E0A72B6F6A14
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfpdrivers.ioctl_nfp_disable, IOCTL_NFP_DISABLE control code [Near-Field Proximity Drivers], IOCTL_NFP_DISABLE, nfpdev/IOCTL_NFP_DISABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfpdev.h
apiname:
-	IOCTL_NFP_DISABLE
product: Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_TECH_ROUTING_INFO, *PSECURE_ELEMENT_TECH_ROUTING_INFO
---

# IOCTL_NFP_DISABLE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


A client sends the <b>IOCTL_NFP_DISABLE</b> request to temporarily disable subscriptions, publications, and presence events. This is useful when a client wants to disable the proximity functionality but keep the resources allocated to quickly re-enable them when needed again.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length


<text></text>



### -output-buffer

None


### -output-buffer-length


<text></text>



### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block


Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].



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
The driver MUST complete all pended <a href="..\nfpdev\ni-nfpdev-ioctl_nfp_get_next_subscribed_message.md">IOCTL_NFP_GET_NEXT_SUBSCRIBED_MESSAGE</a>  requests on that handle with STATUS_CANCELLED.

</li>
</ul>
</li>
<li>
	If a publication handle is “Disabled”, the provider MUST NOT transmit the publication’s message and it MUST complete all pended <a href="..\nfpdev\ni-nfpdev-ioctl_nfp_get_next_transmitted_message.md">IOCTL_NFP_GET_NEXT_TRANSMITTED_MESSAGE</a> requests on that handle with STATUS_CANCELLED

</li>
</ul>




## -see-also

<a href="..\nfpdev\ni-nfpdev-ioctl_nfp_enable.md">IOCTL_NFP_ENABLE</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a>

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_NFP_DISABLE control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

