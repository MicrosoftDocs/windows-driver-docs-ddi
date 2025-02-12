---
UID: NF:pktmonclntk.PktMonClntInitialize
tech.root: 
title: PktMonClntInitialize
ms.date: 02/10/2025
targetos: Windows
description: The PktMonClntInitialize function initializes the kernel driver acting as a Packet Monitor client.
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
 - PktMonClntInitialize
f1_keywords:
 - PktMonClntInitialize
 - pktmonclntk/PktMonClntInitialize
dev_langs:
 - c++
helpviewer_keywords:
 - PktMonClntInitialize
---

## -description

The **PktMonClntInitialize** function initializes the kernel driver acting as a Packet Monitor client, informing Packet Monitor about the module ID that identifies the client, as well as some handlers it makes available for Packet Monitor to call.

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

- [PktMonClntUninitialize](nf-pktmonclntk-pktmonclntinitialize.md)
