---
UID: NC:parallel.PNEGOTIATE_IEEE_MODE
title: PNEGOTIATE_IEEE_MODE (parallel.h)
description: 
old-location: parports\pnegotiate_ieee_mode.htm
tech.root: parports
ms.date: 08/05/2025
keywords: ["PNEGOTIATE_IEEE_MODE callback"]
ms.keywords: PNEGOTIATE_IEEE_MODE, PNEGOTIATE_IEEE_MODE function pointer [Parallel Ports], cisspd_0bea0bb3-2a7c-4cf4-938d-8bc67962a222.xml, parallel/PNEGOTIATE_IEEE_MODE, parports.pnegotiate_ieee_mode
req.header: parallel.h
req.include-header: parallel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
f1_keywords:
 - PNEGOTIATE_IEEE_MODE
 - parallel/PNEGOTIATE_IEEE_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - parallel.h
api_name:
 - PNEGOTIATE_IEEE_MODE
---

# PNEGOTIATE_IEEE_MODE callback

## -description

The old version of the **PNEGOTIATE_IEEE_MODE** callback function. For the latest version, see the **[PNEGOTIATE_IEEE_MODE](./nc-parallel-pnegotiate_ieee_mode~r1.md)** (new) callback function.

## -parameters

### -param Extension [in]

Pointer to the device extension of the parallel port device.

### -param Extensibility [in]

Specifies the IEEE 1284 extensibility mode to negotiate. This is a UCHAR value that indicates the specific parallel port communication mode to establish.

## -returns

Returns an NTSTATUS value. Possible return values include:

| Return code | Description |
|--|--|
| STATUS_SUCCESS| The IEEE mode was successfully negotiated. |
| STATUS_UNSUCCESSFUL | The mode negotiation failed. |
| STATUS_INVALID_PARAMETER | An invalid extensibility mode was specified. |
| STATUS_DEVICE_NOT_READY | The parallel port device is not ready for mode negotiation. |

## -remarks

## -see-also

- **[PNEGOTIATE_IEEE_MODE](./nc-parallel-pnegotiate_ieee_mode~r1.md)**
