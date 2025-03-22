---
UID: NC:prminterface.PRM_LOCK_MODULE
tech.root: kernel
title: PRM_LOCK_MODULE
ms.date: 02/05/2024
targetos: Windows
description: "Locks a PRM module and prevents it from being unloaded."
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: prminterface.h
req.idl: 
req.include-header: 
req.irql: <= HIGH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
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
 - prminterface.h
api_name:
 - PRM_LOCK_MODULE
f1_keywords:
 - PRM_LOCK_MODULE
 - prminterface/PRM_LOCK_MODULE
dev_langs:
 - c++
helpviewer_keywords:
 - PRM_LOCK_MODULE
---

# PRM_LOCK_MODULE function (prminterface.h)

## -description

This routine locks a PRM module in memory and prevents it from being updated by the OS runtime.

## -parameters

### -param HandlerGuid [in]

Supplies the GUID of the PRM handler whose module needs to be locked.

## -returns

This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

PRM_LOCK_MODULE is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a [PRM_INTERFACE](./ns-prminterface-prm_interface.md) structure. Drivers obtain the address of this routine by calling [**ExGetPrmInterface**](./nf-prminterface-exgetprminterface.md).

## -see-also

[Windows Kernel-Mode PRM Library](/windows-hardware/drivers/kernel/windows-kernel-mode-prm-library)