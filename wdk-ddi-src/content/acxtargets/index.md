---
UID: NA:acxtargets
tech.root: audio
title: acxtargets
ms.date: 07/26/2022
targetos: Windows
description: The acxtargets header is used by the ACX audio class extensions.
prerelease: true
req.assembly: 
req.construct-type: apiset
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxtargets.h
api_name:
 - acxtargets
f1_keywords:
 - acxtargets
 - acxtargets/acxtargets
dev_langs:
 - c++
---

## -description

The acxtargets header is used by the ACX audio class extensions. For more information, see [ACX Audio Class Extensions overview](/windows-hardware/drivers/audio/acx-audio-class-extensions-overview).

[WdfIoTarget](/windows-hardware/drivers/ddi/wdfiotarget/) is a WDF abstraction to facilitate the communication between two different stacks. ACX uses WdfIoTarget to facilitate communications between ACX objects, circuits, pins, streams, elements and circuit factories.

ACX uses the following ACX Objects to support communications between targets. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

Drivers use *AcxTargetCircuit* to communicate with a remote circuit exposed by a different stack. AcxTargetCircuit is implemented using a WdfIoTarget.

Drivers use *AcxTargetPin* to communicate with a remote circuit’s pin exposed by a different stack. AcxTargetPin is implemented using a WdfIoTarget to send messages to the remote pin entity.

Drivers use *AcxTargetStream* to communicate with a remote circuit’s stream exposed by a different stack. AcxTargetStream is implemented using a WdfIoTarget to create a remote stream and change the state of the remote stream.

Drivers use *AcxTargetElement* to communicate with a remote circuit’s element exposed by a different stack. AcxTargetElement is implemented using a WdfIoTarget to send messages to the remote element entity.

Drivers use *AcxTargetFactoryCircuit* to communicate with a remote circuit factory instance. AcxTargetFactoryCircuit is implemented using a WdfIoTarget to send messages to the remote circuit factory.

To interact with the remote circuit, each of the above ACX types supports:

- properties
- methods 
- events
 
For more information, see:

- [ACX Audio Class Extensions overview](/windows-hardware/drivers/audio/acx-audio-class-extensions-overview)

- [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)
 
- [Audio](../_audio/index.md)

READY2GO

EDITCOMPLETE
