---
UID: NF:ntifs.FsRtlCheckFileSystemFilterCallbacksRegistered
tech.root: ifsk
title: FsRtlCheckFileSystemFilterCallbacksRegistered
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the FsRtlCheckFileSystemFilterCallbacksRegistered function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
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
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlCheckFileSystemFilterCallbacksRegistered
f1_keywords:
 - FsRtlCheckFileSystemFilterCallbacksRegistered
 - ntifs/FsRtlCheckFileSystemFilterCallbacksRegistered
dev_langs:
 - c++
helpviewer_keywords:
 - FsRtlCheckFileSystemFilterCallbacksRegistered
---

## -description

The **FsRtlCheckFileSystemFilterCallbacksRegistered** routine checks whether the driver object has already registered file system filter callbacks under its driver extension field.

## -parameters

### -param FilterDriverObject

[in] Pointer to the driver object for the filter driver or filesystem that might have registered file system filter callbacks.

## -returns

**FsRtlCheckFileSystemFilterCallbacksRegistered** returns TRUE if the driver object has already registered file system filter callbacks; otherwise, it returns FALSE.
