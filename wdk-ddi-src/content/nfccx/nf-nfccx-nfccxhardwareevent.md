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
ms.keywords: NfcCxHardwareEvent, NfcCxHardwareEvent method [Near-Field Proximity Drivers], nfccx/NfcCxHardwareEvent, nfpdrivers._nfccxhardwareevent
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NfcCx.dll
api_name:
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
<li>The client driver should synchronize the work item with other device callbacks. This is typically achieved by AutomaticSerialization option in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553086">WDF_WORKITEM_CONFIG</a> and have the parent of the WDFWORKITEM be the WDFDEVICE or by having the work item callback explicitly taking the device lock i.e. <a href="https://msdn.microsoft.com/library/windows/hardware/ff548721">WdfObjectAcquireLock</a> on the WDFDEVICE.</li>
<li>If the hardware event call fails from a work-item, the client driver should either restart or unlock the driver to prevent it from being in a bad state. This can be achieved using the Restart or Unload option.</li>
</ul>

## -parameters




### -param Device

A handle to a framework device object.


### -param HardwareEvent

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn905543">NFC_CX_HARDWARE_EVENT</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.




## -see-also




<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

