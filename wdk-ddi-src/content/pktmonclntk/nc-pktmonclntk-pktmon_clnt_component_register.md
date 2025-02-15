---
UID: NC:pktmonclntk.PKTMON_CLNT_COMPONENT_REGISTER
tech.root: netvista
title: PKTMON_CLNT_COMPONENT_REGISTER
ms.date: 02/13/2025
targetos: Windows
description: 
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
 - LibDef
api_location:
 - pktmonclntk.h
api_name:
 - PKTMON_CLNT_COMPONENT_REGISTER
f1_keywords:
 - PKTMON_CLNT_COMPONENT_REGISTER
 - pktmonclntk/PKTMON_CLNT_COMPONENT_REGISTER
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_COMPONENT_REGISTER
---

## -description

This callback function is invoked when a component is registered with Packet Monitor. Such registrations create a context used to report packet drops. This context helps to identify its relative position on the networking stack, as well as a packet type.

## -parameters

### -param CompContext

Pointer to PKTMON_COMPONENT_CONTEXT which holds the context for the component. This structure should be zero-initialized before PktMonClntComponentRegister is called, and PktMonClntComponentRegister will fill in the structure as needed.

### -param Name

The Packet Monitor client's name.

### -param Description

A description for the Packet Monitor client.

### -param ComponentType

The type associated with this component. This must be one of the values defined in the PKTMON_COMPONENT_TYPE enumeration.

### -param PacketType

The payload type this client deals with. This must be one of the values defined in the PKTMON_PACKET_TYPE enumeration.

## -returns

If the function succeeds, it returns STATUS_SUCCESS. Otherwise, it returns a NTSTATUS error code.

## -remarks

After the component is done and will not be used anymore the Packet Monitor client should call PktMonClntComponentUnregister to let Packet Monitor know about that.

## -see-also

- [PktMonClntInitialize]()
- [PktMonClntUninitialize]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
