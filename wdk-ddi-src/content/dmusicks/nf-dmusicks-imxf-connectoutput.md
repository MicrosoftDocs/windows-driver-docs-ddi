---
UID: NF:dmusicks.IMXF.ConnectOutput
title: IMXF::ConnectOutput (dmusicks.h)
description: The ConnectOutput method connects this IMXF interface with the sink specified by the pSinkMXF parameter.
tech.root: audio
ms.assetid: cca02916-afd0-47a5-a19a-1c3159c54ed4
ms.date: 10/31/2018
ms.topic: method
f1_keywords:
 - "dmusicks/IMXF.ConnectOutput"
ms.keywords: IMXF::ConnectOutput, ConnectOutput, IMXF.ConnectOutput, IMXF::ConnectOutput, IMXF.ConnectOutput
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
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - dmusicks.h
api_name: 
 - IMXF.ConnectOutput
product: 
 - Windows
targetos: Windows

---

# IMXF::ConnectOutput


## -description

The ConnectOutput method connects this IMXF interface with the sink specified by the pSinkMXF parameter.

## -parameters

### -param sinkMXF

Pointer to the destination (sink) IMXF interface we are connecting to in the port driver.



## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

## -see-also

[IMXF](nn-dmusicks-imxf.md)
