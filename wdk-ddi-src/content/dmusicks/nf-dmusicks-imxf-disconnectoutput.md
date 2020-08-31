---
UID: NF:dmusicks.IMXF.DisconnectOutput
title: IMXF::DisconnectOutput (dmusicks.h)
description: The DisconnectOutput method disconnects this IMXF interface from the synth sink or capture sink.
tech.root: audio
ms.assetid: 65b18277-7b28-455c-ae39-81d97a09e21b
ms.date: 10/31/2018
keywords: ["IMXF::DisconnectOutput"]
ms.keywords: IMXF::DisconnectOutput, DisconnectOutput, IMXF.DisconnectOutput, IMXF::DisconnectOutput, IMXF.DisconnectOutput
req.header: dmusicks.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IMXF::DisconnectOutput
 - dmusicks/IMXF::DisconnectOutput
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IMXF.DisconnectOutput
product:
 - Windows
---

# IMXF::DisconnectOutput


## -description

The DisconnectOutput method disconnects this IMXF interface from the synth sink or capture sink.

## -parameters

### -param sinkMXF

Pointer to the destination (sink) IMXF interface that we are disconnecting from.

## -returns

This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

This method zeros the pSinkMXF location that was previously filled in by the IMXF::ConnectOutput call.

Output will go to the allocator from the time that DisconnectOutput is called until ConnectOutput is called again.

## -see-also

[IMXF](nn-dmusicks-imxf.md)

