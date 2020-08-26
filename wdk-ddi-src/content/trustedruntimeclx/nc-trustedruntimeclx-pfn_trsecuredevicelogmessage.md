---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICELOGMESSAGE
title: PFN_TRSECUREDEVICELOGMESSAGE (trustedruntimeclx.h)
description: 
ms.assetid: 796ac627-fd80-4074-bcf3-a7c23108d518
ms.date: 10/19/2018
keywords: ["*PFN_TRSECUREDEVICELOGMESSAGE callback function"]
f1_keywords:
 - "trustedruntimeclx/*PFN_TRSECUREDEVICELOGMESSAGE"
 - "*PFN_TRSECUREDEVICELOGMESSAGE"
req.header: trustedruntimeclx.h
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- trustedruntimeclx.h
api_name: 
- PFN_TRSECUREDEVICELOGMESSAGE
targetos: Windows
ms.custom: RS5
---

# *PFN_TRSECUREDEVICELOGMESSAGE callback function

## -description

 

## -syntax

```cpp
//Declaration

*PFN_TRSECUREDEVICELOGMESSAGE *PfnTrsecuredevicelogmessage; 

// Definition

NTSTATUS *PfnTrsecuredevicelogmessage 
(
	WDFOBJECT BindContext
	WDFDEVICE Device
	ULONG Severity
	PCSTR Message
	va_list Arguments
)
{...}

```

## -parameters

### -param BindContext: 
### -param Device: 
### -param Severity: 
### -param Message: 
### -param Arguments: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks




## -see-also
