---
UID: NF:pktmonclntk.PktMonClntComponentRegister
tech.root: 
title: PktMonClntComponentRegister
ms.date: 02/10/2025
targetos: Windows
description: The PktMonClntComponentRegister function is used to register a component with Packet Monitor.
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

The **PktMonClntComponentRegister** function is used to register a component with Packet Monitor. Such registrations create a context used to report packet drops. This context helps to identify its relative position on the networking stack, as well as a packet type.

## -parameters

### -param CompContext

Pointer to the **[PKTMON_COMPONENT_CONTEXT](ns-pktmonclntk-pktmon_component_context.md)** that holds the context for the component. Zero-initialize this structure before calling **PktMonClntComponentRegister**, which fills in the structure.

### -param Name

The Packet Monitor client's name.

### -param Description

A description for the Packet Monitor client.

### -param Type

The type associated with this component. This must be one of the values defined in the PKTMON_COMPONENT_TYPE enumeration.

### -param PacketType

The payload type this client deals with. This must be one of the values defined in the PKTMON_PACKET_TYPE enumeration.

## -returns

If the function succeeds, it returns STATUS_SUCCESS. Otherwise, it returns a NTSTATUS error code.

## -remarks

After the component is done and will not be used anymore the Packet Monitor client should call PktMonClntComponentUnregister to let Packet Monitor know about that.

## -see-also

- [PktMonClntComponentUnregister](nf-pktmonclntk-pktmonclntcomponentunregister.md)
