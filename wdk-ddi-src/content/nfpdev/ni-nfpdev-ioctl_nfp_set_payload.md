---
UID: NI:nfpdev.IOCTL_NFP_SET_PAYLOAD
title: IOCTL_NFP_SET_PAYLOAD
author: windows-driver-content
description: A client application sends message data and confirms publication with the IOCTL_NFP_SET_PAYLOAD request.
old-location: nfpdrivers\ioctl_nfp_set_payload.htm
old-project: nfpdrivers
ms.assetid: FF89A868-1289-4D1D-BFA8-17E65ED7F8C4
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfpdrivers.ioctl_nfp_set_payload, IOCTL_NFP_SET_PAYLOAD control code [Near-Field Proximity Drivers], IOCTL_NFP_SET_PAYLOAD, nfpdev/IOCTL_NFP_SET_PAYLOAD
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
-	IOCTL_NFP_SET_PAYLOAD
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO"
---

# IOCTL_NFP_SET_PAYLOAD IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


A client application sends message data and confirms publication with the <b>IOCTL_NFP_SET_PAYLOAD</b> request.


## -ioctlparameters




### -input-buffer

The input buffer contains the message data to transmit.


### -input-buffer-length


<text></text>



### -output-buffer

None.


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


The following actions are required when using this IOCTL:<ul>
<li>
If this IOCTL is sent on a handle that hasn’t previously been opened on a “Pubs\...” filename, the driver MUST complete it with STATUS_INVALID_DEVICE_STATE.

</li>
<li>
The message data is write-once.  If this IOCTL succeeds once, any subsequent IOCTL_NFP_SET_PAYLOAD received on the same handle MUST be completed with STATUS_INVALID_DEVICE_STATE.

</li>
<li>
If the IOCTL contains an output buffer, the driver MUST complete the IOCTL with STATUS_INVALID_PARAMETER.

</li>
<li>
If the input buffer is larger than the driver’s maximum message size, the driver MUST complete the IOCTL with STATUS_INVALID_BUFFER_SIZE.

</li>
<li>
If any device becomes proximate after this IOCTL succeeds, and before the handle is closed, then the message data (along with its type) MUST be transmitted only once to the proximate device.

</li>
<li>
If the same (or different) device becomes proximate again before the handle is closed, the message MUST be transmitted once again.

</li>
<li>
If a device is currently proximate when this IOCTL is successfully completed, then the message data (along with its type) MUST be transmitted (only once) to the proximate device.  This applies even if the handle is immediately closed.

</li>
</ul>




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_NFP_SET_PAYLOAD control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

