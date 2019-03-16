---
UID: NC:trustedruntimeclx.EVT_TR_PREPARE_HARDWARE_SECURE_ENVIRONMENT
title: EVT_TR_PREPARE_HARDWARE_SECURE_ENVIRONMENT (trustedruntimeclx.h)
description: 
ms.assetid: 5c4f51c6-76a8-4010-b858-526099e52d73
ms.date: 10/19/2018
ms.topic: callback
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
- EVT_TR_PREPARE_HARDWARE_SECURE_ENVIRONMENT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_PREPARE_HARDWARE_SECURE_ENVIRONMENT callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_PREPARE_HARDWARE_SECURE_ENVIRONMENT EvtTrPrepareHardwareSecureEnvironment; 

// Definition

NTSTATUS EvtTrPrepareHardwareSecureEnvironment 
(
	WDFDEVICE MasterDevice
	WDFCMRESLIST RawResources
	WDFCMRESLIST TranslatedResources
)
{...}

```

## -parameters

### -param MasterDevice: 
### -param RawResources: 
### -param TranslatedResources: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
