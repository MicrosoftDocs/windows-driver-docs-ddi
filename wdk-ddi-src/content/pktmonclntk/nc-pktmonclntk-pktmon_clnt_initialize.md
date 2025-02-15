---
UID: NC:pktmonclntk.PKTMON_CLNT_INITIALIZE
tech.root: netvista
title: PKTMON_CLNT_INITIALIZE
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
 - PKTMON_CLNT_INITIALIZE
f1_keywords:
 - PKTMON_CLNT_INITIALIZE
 - pktmonclntk/PKTMON_CLNT_INITIALIZE
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_CLNT_INITIALIZE
---

## -description

This callback function is invoked when the kernel driver acting as a Packet Monitor client is initialized, informing Packet Monitor about the module ID that identifies the client, as well as some handlers it makes available for Packet Monitor to call.

## -parameters

### -param ModuleId

An NPI_MODULEID used to identify the Packet Monitor client.

### -param EnumComponents

A handler that Packet Monitor should call to enumerate components.

### -param CleanupComponents

A handler that Packet Monitor should call to cleanup components. Can be NULL.

### -param NotifyComponent

A handler that Packet Monitor should call to notify a component. Can be NULL.

## -returns

If the function succeeds, it returns STATUS_SUCCESS. Otherwise, it returns a NTSTATUS error code.

## -remarks

This function should be called only once per module. PktMonClntUninitialize should be called to uninitialize the driver before it exits. After the Packet Monitor client is done and does not wish to interact with Packet Monitor anymore, it should call PktMonClntUninitialize.

## -see-also

- [PktMonClntUninitialize]()
- [PktMonClntComponentRegister]()
- [PktMonClntComponentUnregister]()
- [PktMonClntSetComponentProperty]()
- [PktMonClntAddEdge]()
- [PktMonClntNblLog]()
- [PktMonClntNblDrop]()
- [PktMonClntHeaderInfoLog]()
- [PktMonClntHeaderInfoDrop]()
