---
UID: NS:nfccx._NFC_CX_HARDWARE_EVENT
title: _NFC_CX_HARDWARE_EVENT (nfccx.h)
description: The NFC_CX_HARDWARE_EVENT structure is an input parameter to NfcCxHardwareEvent.
old-location: nfpdrivers\nfc_cx_hardware_event.htm
tech.root: nfpdrivers
ms.assetid: FC7566C0-95FD-450C-897E-C57870386512
ms.date: 02/15/2018
keywords: ["_NFC_CX_HARDWARE_EVENT structure"]
ms.keywords: "*PNFC_CX_HARDWARE_EVENT, NFC_CX_HARDWARE_EVENT, NFC_CX_HARDWARE_EVENT structure [Near-Field Proximity Drivers], PNFC_CX_HARDWARE_EVENT, PNFC_CX_HARDWARE_EVENT structure pointer [Near-Field Proximity Drivers], _NFC_CX_HARDWARE_EVENT, nfccx/NFC_CX_HARDWARE_EVENT, nfccx/PNFC_CX_HARDWARE_EVENT, nfpdrivers.nfc_cx_hardware_event"
f1_keywords:
 - "nfccx/NFC_CX_HARDWARE_EVENT"
 - "NFC_CX_HARDWARE_EVENT"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- nfccx.h
api_name:
- NFC_CX_HARDWARE_EVENT
targetos: Windows
req.typenames: NFC_CX_HARDWARE_EVENT, *PNFC_CX_HARDWARE_EVENT
---

# _NFC_CX_HARDWARE_EVENT structure


## -description


The NFC_CX_HARDWARE_EVENT structure is an input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/nf-nfccx-nfccxhardwareevent">NfcCxHardwareEvent.</a>



## -struct-fields




### -field HardwareStatus

An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS </a> value.


### -field HostAction

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_host_action">NFC_CX_HOST_ACTION</a>-typed enumerator.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

