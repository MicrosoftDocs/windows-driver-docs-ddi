---
UID: NC:dispmprt.DXGKDDI_CONTROLDIAGNOSTICREPORTING
title: DXGKDDI_CONTROLDIAGNOSTICREPORTING
author: windows-driver-content
description: 
ms.assetid: 71b4cc86-0fe6-459d-b317-6630565e9ae5
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
-	DXGKDDI_CONTROLDIAGNOSTICREPORTING
product: Windows
targetos: Windows
---

# DXGKDDI_CONTROLDIAGNOSTICREPORTING callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

DXGKDDI_CONTROLDIAGNOSTICREPORTING DxgkddiControldiagnosticreporting; 

// Definition

NTSTATUS DxgkddiControldiagnosticreporting 
(
	IN_CONST_PVOID MiniportDeviceContext
	IN_PDXGKARG_CONTROLDIAGNOSTICREPORTING pArgControlDiagnosticReporting
)
{...}

DXGKDDI_CONTROLDIAGNOSTICREPORTING *PDXGKDDI_CONTROLDIAGNOSTICREPORTING


```

## -parameters

### -param MiniportDeviceContext: 
### -param pArgControlDiagnosticReporting: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also