---
UID: NC:nfccx.EVT_NFC_CX_WRITE_NCI_PACKET
title: EVT_NFC_CX_WRITE_NCI_PACKET
author: windows-driver-content
description: Called by the NFC CX to send a write packet to the client driver.
old-location: nfpdrivers\evtnfccxwritencipacket.htm
old-project: nfpdrivers
ms.assetid: B734439A-E345-44CC-8FD0-8E38A718A773
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: EVT_NFC_CX_WRITE_NCI_PACKET, EvtNfcCxWriteNciPacket, EvtNfcCxWriteNciPacket callback function [Near-Field Proximity Drivers], nfccx/EvtNfcCxWriteNciPacket, nfpdrivers.evtnfccxwritencipacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: Requires same
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	nfccx.h
apiname:
-	EvtNfcCxWriteNciPacket
product: Windows
targetos: Windows
req.typenames: NET_PNP_EVENT, *PNET_PNP_EVENT
---

# EVT_NFC_CX_WRITE_NCI_PACKET callback


## -description


Called by the NFC CX to send a write packet to the client driver. The request code must match IOCTL_NFCCX_WRITE_PACKET. 


## -prototype


````
EVT_NFC_CX_WRITE_NCI_PACKET EvtNfcCxWriteNciPacket;

void EvtNfcCxWriteNciPacket(
  _In_ WDFDEVICE  Device,
  _In_ WDFREQUEST Request
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object.


## -returns



This callback function does not return a value.




## -remarks



The client driver should not make any blocking calls when handling this function call. Any I/O processing must be handled on a separate thread or work-item (that is, the client driver should immediately return STATUS_PENDING and on completion invoke the completion handler).




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20EVT_NFC_CX_WRITE_NCI_PACKET callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

