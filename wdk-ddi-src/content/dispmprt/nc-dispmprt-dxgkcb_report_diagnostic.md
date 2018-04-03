---
UID: NC:dispmprt.DXGKCB_REPORT_DIAGNOSTIC
title: DXGKCB_REPORT_DIAGNOSTIC
author: windows-driver-content
description: 
ms.assetid: 1c38189b-daaf-4d55-826a-5e868a0e1190
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	dispmprt.h
apiname: 
-	DXGKCB_REPORT_DIAGNOSTIC
product: Windows
targetos: Windows
---

# DXGKCB_REPORT_DIAGNOSTIC callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGKCB_REPORT_DIAGNOSTIC DxgkcbReportDiagnostic; 

// Definition

_IRQL_requires_same_ DxgkcbReportDiagnostic 
(
	HANDLE DeviceHandle
	IN_PDXGK_DIAGNOSTIC_HEADER pDiagnostic
)
{...}

DXGKCB_REPORT_DIAGNOSTIC 


```

## -parameters

### -param DeviceHandle: 
### -param pDiagnostic: 



## -returns

Returns _IRQL_requires_same_ that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also