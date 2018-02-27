---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SET_PROTOCOL
title: IOCTL_SMARTCARD_SET_PROTOCOL
author: windows-driver-content
description: Sets the procotol the driver communicates to the smart card with after the card is detected.
old-location: nfpdrivers\ioctl_smartcard_set_protocol.htm
old-project: nfpdrivers
ms.assetid: 9A54D427-128F-41C1-B6BD-EE09B0402C32
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SMARTCARD_SET_PROTOCOL, IOCTL_SMARTCARD_SET_PROTOCOL control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_set_protocol, winsmcrd/IOCTL_SMARTCARD_SET_PROTOCOL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: winsmcrd.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsmcrd.h
apiname:
-	IOCTL_SMARTCARD_SET_PROTOCOL
product: Windows
targetos: Windows
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_SET_PROTOCOL IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


Sets the procotol the driver communicates to the smart card with after the card is detected.


## -ioctlparameters




### -input-buffer

(DWORD) mask of protocols below:<ul>
<li>SCARD_PROTOCOL_T1</li>
<li>SCARD_PROTOCOL_DEFAULT</li>
<li>SCARD_PROTOCOL_OPTIMAL</li>
</ul>



### -input-buffer-length



<text></text>




### -output-buffer

(DWORD) contains the selected protocol (for example, SCARD_PROTOCOL_T1).


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




## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_SET_PROTOCOL control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

