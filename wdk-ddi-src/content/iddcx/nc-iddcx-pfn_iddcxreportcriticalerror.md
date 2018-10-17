---
UID: NC:iddcx.PFN_IDDCXREPORTCRITICALERROR
title: *PFN_IDDCXREPORTCRITICALERROR
author: windows-driver-content
description: An OS callback function the driver calls to report a critical error.
ms.assetid: f4b2190f-f005-47bb-8b67-82701985e887
ms.date:
ms.topic: callback
req.header: iddcx.h
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
-	iddcx.h
apiname:
-	*PFN_IDDCXREPORTCRITICALERROR
product: 
- Windows
targetos: Windows
---

# *PFN_IDDCXREPORTCRITICALERROR callback function

An OS callback function the driver calls to report a critical error.

## -description

Implemented by the client driver to ...

## -prototype

```
//Declaration

*PFN_IDDCXREPORTCRITICALERROR *PfnIddcxreportcriticalerror;

// Definition

NTSTATUS *PfnIddcxreportcriticalerror
(
	PIDD_DRIVER_GLOBALS DriverGlobals
	IDDCX_ADAPTER AdapterObject
	CONST IDARG_IN_REPORTCRITICALERROR *pInArgs
)
{...}

*PFN_IDDCXREPORTCRITICALERROR


```

## -parameters

### -param DriverGlobals [in]

Contains system-defined per-driver data.

### -param AdapterObject [in, opt]

The adapter object that is the critical error occurred on. If the error occurred before a IddCxAdapter was created, pass in nullptr for this value.

### -param *pInArgs [in]

Input arguments to the function.

## -returns

If the routine succeeds, it never returns to the driver as the driver process will be terminated.

## -remarks

The OS will bug check the driver with the following bug check code:

```cpp
(pInArgs->MajorErrorCode+0x100 << 8) + pInArgs->MinorErrorCode
```

A Watson dump will be generated and driver process will terminate and restart according the UMDF driver restart policy. As a user mode memory dump is generated the driver should place any useful debug info on the stack of the function that calls this callback.


## -see-also
