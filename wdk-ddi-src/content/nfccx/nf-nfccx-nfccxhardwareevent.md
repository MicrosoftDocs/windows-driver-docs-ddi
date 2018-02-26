---
UID: NF:nfccx.NfcCxHardwareEvent
title: NfcCxHardwareEvent function
author: windows-driver-content
description: Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following:
old-location: nfpdrivers\_nfccxhardwareevent.htm
old-project: nfpdrivers
ms.assetid: 5D108897-93D9-4C67-9138-86C608AD8C4C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , C, E, H, N, NfcCxHardwareEvent, NfcCxHardwareEvent method [Near-Field Proximity Drivers], a, c, d, e, f, n, nfccx/NfcCxHardwareEvent, nfpdrivers._nfccxhardwareevent, r, t, v, w, x"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NfcCx.dll
apiname:
-	NfcCxHardwareEvent
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---

# NfcCxHardwareEvent function


## -description


Called by the client driver when a hardware event occurs like D0Entry and D0Exit callbacks to start or stop the device. For drivers that require firmware download on initialization or boot-up, it is recommended to move this call to a separate work item. However, the client driver is responsible for the following:
<ul>
<li>The client driver should take an idle power reference before queueing the work item. The reference needs to be dropped when the work item completes. This ensures idle power management doesnt cause the driver to go into D3 while the work-item is running.</li>
<li>The client driver should synchronize the work item with other device callbacks. This is typically achieved by AutomaticSerialization option in <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> and have the parent of the WDFWORKITEM be the WDFDEVICE or by having the work item callback explicitly taking the device lock i.e. <a href="https://msdn.microsoft.com/library/windows/hardware/ff548721">WdfObjectAcquireLock</a> on the WDFDEVICE.</li>
<li>If the hardware event call fails from a work-item, the client driver should either restart or unlock the driver to prevent it from being in a bad state. This can be achieved using the Restart or Unload option.</li>
</ul>

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




## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxHardwareEvent method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

