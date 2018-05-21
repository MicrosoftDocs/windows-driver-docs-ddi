---
UID: NC:dispmprt.DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
title: DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
author: windows-driver-content
description: 
ms.assetid: ad14a3b9-d0bf-4292-8e53-7f51544d96c5
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
-	DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
product: Windows
targetos: Windows
---

# DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT DxgkddiQuerydiagnostictypessupport; 

// Definition

NTSTATUS DxgkddiQuerydiagnostictypessupport 
(
	IN_CONST_PVOID MiniportDeviceContext
	INOUT_PDXGKARG_QUERYDIAGNOSTICTYPESSUPPORT pArgQueryDiagnosticTypesSupport
)
{...}

DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT *PDXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT


```

## -parameters

### -param MiniportDeviceContext: 
### -param pArgQueryDiagnosticTypesSupport: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also