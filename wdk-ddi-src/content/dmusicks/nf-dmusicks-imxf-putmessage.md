---
UID: NF:dmusicks.IMXF.PutMessage
title: IMXF::PutMessage (dmusicks.h)
description: The PutMessage method passes a DMUS_KERNEL_EVENT structure to its next destination.
tech.root: audio
ms.assetid: 0ef3df3c-c340-49d5-947f-590767e6f02f
ms.date: 10/31/2018
f1_keywords:
 - "dmusicks/IMXF.PutMessage"
ms.keywords: IMXF::PutMessage, PutMessage, IMXF.PutMessage, IMXF::PutMessage, IMXF.PutMessage
req.header: dmusicks.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - dmusicks.h
api_name: 
 - IMXF.PutMessage
product: 
 - Windows
targetos: Windows

---

# IMXF::PutMessage


## -description

The PutMessage method passes a DMUS_KERNEL_EVENT structure to its next destination. The miniport driver uses this method to discard used event structures so that they can be recycled by the allocator.

Syntax

## -parameters

### -param pDMKEvt

Pointer to the DMUS_KERNEL_EVENT structure being passed to its destination.


## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks
During rendering, the miniport driver calls the PutMessage method to discard used DMUS_KERNEL_EVENT structures. The method routes the discarded structures to the allocator for reuse. The miniport driver calls this method once it has extracted the MIDI data from the structures for rendering.

During MIDI capture, this method is used to package and pass MIDI messages to the DMus port driver's capture sink, as shown in the figure in MIDI Transport. These messages can be single, multiple, or fragmentary MIDI events and are packaged in DMUS_KERNEL_EVENT structures (which are retrieved by IAllocatorMXF::GetMessage calls).

The allocator is always the last destination in any chain, so every DMUS_KERNEL_EVENT structure will eventually be recycled. If IMXF::ConnectOutput has not been called, PutMessage will default to passing the structure to the allocator. For more information, see Allocator. 


## -see-also

[IMXF](nn-dmusicks-imxf.md)
