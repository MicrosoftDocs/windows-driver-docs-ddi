---
UID: NC:ntddk.SILO_CONTEXT_CLEANUP_CALLBACK
title: SILO_CONTEXT_CLEANUP_CALLBACK (ntddk.h)
description: This callback is invoked when the context object reaches a reference count of zero.
old-location: kernel\silo_context_cleanup_callback.htm
tech.root: kernel
ms.assetid: 452E63E8-DFBB-43AF-81F4-0405C3EF74CE
ms.date: 04/30/2018
keywords: ["SILO_CONTEXT_CLEANUP_CALLBACK callback function"]
ms.keywords: CleanupCallback, CleanupCallback callback function [Kernel-Mode Driver Architecture], SILO_CONTEXT_CLEANUP_CALLBACK, SILO_CONTEXT_CLEANUP_CALLBACK callback, kernel.silo_context_cleanup_callback, ntddk/CleanupCallback
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
req.typenames: 
f1_keywords:
 - SILO_CONTEXT_CLEANUP_CALLBACK
 - ntddk/SILO_CONTEXT_CLEANUP_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - CleanupCallback
---

# SILO_CONTEXT_CLEANUP_CALLBACK callback function


## -description

This callback is invoked when the context object reaches a reference count of zero.

## -parameters

### -param SiloContext 

[in]
A pointer provided by the user with the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a>.

