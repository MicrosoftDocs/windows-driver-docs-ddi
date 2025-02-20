---
UID: NF:pktmonclntk.PktMonClntComponentRegister
tech.root: netvista
title: PktMonClntComponentRegister
ms.date: 02/13/2025
targetos: Windows
description: The PktMonClntComponentRegister function registers a component with Packet Monitor, allowing it to monitor and report packet activities.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntk.h
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
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntk.h
api_name:
 - PktMonClntComponentRegister
f1_keywords:
 - PktMonClntComponentRegister
 - pktmonclntk/PktMonClntComponentRegister
dev_langs:
 - c++
helpviewer_keywords:
 - PktMonClntComponentRegister
---

## -description

The **PktMonClntComponentRegister** function registers a component with Packet Monitor, allowing it to monitor and report packet activities.

## -parameters

### -param CompContext

Pointer to the **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** that holds the context for the component. Zero-initialize this structure before calling **PktMonClntComponentRegister**, which fills in the structure.

### -param Name

The Packet Monitor client's name.

### -param Description

A description for the Packet Monitor client.

### -param Type

The type associated with this component. This must be one of the values defined in the **[PKTMON_COMPONENT_TYPE](../pktmondefk/ne-pktmondefk-pktmon_component_type.md)** enumeration.

### -param PacketType

The payload type this client deals with. This must be one of the values defined in the **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)** enumeration.

## -returns

If the function succeeds, it returns `STATUS_SUCCESS`. Otherwise, it returns a `NTSTATUS` error code.

## -remarks

When the component is no longer needed, the Packet Monitor client should call **[PktMonClntComponentUnregister](nf-pktmonclntk-pktmonclntcomponentunregister.md)** to unregister it from Packet Monitor and free any associated resources.

## -see-also

- **[PKTMON_COMPONENT_CONTEXT](../pktmonclntk/ns-pktmonclntk-pktmon_component_context.md)**
- **[PKTMON_COMPONENT_TYPE](../pktmondefk/ne-pktmondefk-pktmon_component_type.md)**
- **[PKTMON_PACKET_TYPE](../pktmonnpik/ne-pktmonnpik-pktmon_packet_type.md)**
- **[PktMonClntComponentUnregister](nf-pktmonclntk-pktmonclntcomponentunregister.md)**

### Example

```cpp
PKTMON_COMPONENT_CONTEXT PktMonComp = { 0 };

NTSTATUS
PktMonApiTstRegisterComponent(VOID)
{
    NTSTATUS status = STATUS_SUCCESS;

    DECLARE_CONST_UNICODE_STRING(DriverName, L"pktmonapitst.sys");
    DECLARE_CONST_UNICODE_STRING(Description, L"Sample driver to report packet drops to pktmon.sys");

    status = PktMonClntComponentRegister(
        &PktMonComp,
        &DriverName,
        &Description,
        PktMonComp_IpInterface,
        PktMonPayload_IP);

if (!NT_SUCCESS(status)) {
        // Log error
    }

    return status;
}
```
