---
UID: NF:nfccx.NfcCxHardwareEvent
title: NfcCxHardwareEvent function
author: windows-driver-content
description: Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following:
old-location: nfpdrivers\_nfccxhardwareevent.htm
old-project: nfpdrivers
ms.assetid: 5D108897-93D9-4C67-9138-86C608AD8C4C
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: NfcCxHardwareEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NfcCxHardwareEvent
req.alt-loc: NfcCx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nfccxstub.lib
req.dll: NfcCx.dll
req.irql: 
req.typenames: *PNFC_CX_TRANSPORT_TYPE, NFC_CX_TRANSPORT_TYPE
---

# NfcCxHardwareEvent function



## -description
Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following:



## -syntax

````
NTSTATUS NfcCxHardwareEvent(
   WDFDEVICE              Device,
   PNFC_CX_HARDWARE_EVENT HardwareEvent
);
````


## -parameters

### -param Device 

A handle to a framework device object.


### -param HardwareEvent 

A pointer to an <a href="..\nfccx\ns-nfccx-_nfc_cx_hardware_event.md">NFC_CX_HARDWARE_EVENT</a> structure.


## -returns
If the operation succeeds, the function returns STATUS_SUCCESS.


## -remarks


## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxHardwareEvent method%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

