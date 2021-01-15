---
UID: NC:nfccx.EVT_NFC_CX_SEQUENCE_HANDLER
title: EVT_NFC_CX_SEQUENCE_HANDLER (nfccx.h)
description: Called by the NFC CX to notify the client driver to handle the specific registered sequence.
old-location: nfpdrivers\evtnfccxsequencehandler.htm
tech.root: nfpdrivers
ms.date: 02/15/2018
keywords: ["EVT_NFC_CX_SEQUENCE_HANDLER callback function"]
ms.keywords: "*PFN_NFC_CX_SEQUENCE_HANDLER, EVT_NFC_CX_SEQUENCE_HANDLER, EVT_NFC_CX_SEQUENCE_HANDLER callback, EvtNfcCxSequenceHandler, EvtNfcCxSequenceHandler callback function [Near-Field Proximity Drivers], nfccx/ EvtNfcCxSequenceHandler, nfpdrivers.evtnfccxsequencehandler"
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_NFC_CX_SEQUENCE_HANDLER
 - nfccx/EVT_NFC_CX_SEQUENCE_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - nfccx.h
api_name:
 - EVT_NFC_CX_SEQUENCE_HANDLER
---

# EVT_NFC_CX_SEQUENCE_HANDLER callback function


## -description

Called by the NFC CX to notify the client driver to handle the specific registered sequence.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Sequence 

[in]
An <a href="/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_sequence">NFC_CX_SEQUENCE</a> enumeration.

### -param CompletionRoutine 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function.

### -param CompletionContext 

[in, optional]
Driver-defined context information that the driver specified when it registered the <i>EvtNfcCxSequenceHandler</i> callback function.

## -remarks

On completion of handling the sequence, the client driver notifies the NFC CX through the sequence completion callback. Similar to <a href="/windows-hardware/drivers/ddi/nfccx/nc-nfccx-evt_nfc_cx_write_nci_packet">EvtNfcCxWriteNciPacket</a>, the client must not make any blocking calls when handling this function call. Any I/O processing must be handled on a separate thread or work item. However, the client driver can invoke the completion routine with a status flag when handling this call.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>

