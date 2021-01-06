---
UID: NC:ntddk.SILO_MONITOR_CREATE_CALLBACK
title: SILO_MONITOR_CREATE_CALLBACK (ntddk.h)
description: This is callback is invoked when a new silo is created.
old-location: kernel\silo_monitor_create_callback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["SILO_MONITOR_CREATE_CALLBACK callback function"]
ms.keywords: CreateCallback, CreateCallback callback function [Kernel-Mode Driver Architecture], SILO_MONITOR_CREATE_CALLBACK, SILO_MONITOR_CREATE_CALLBACK callback, kernel.silo_monitor_create_callback, ntddk/CreateCallback
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
 - SILO_MONITOR_CREATE_CALLBACK
 - ntddk/SILO_MONITOR_CREATE_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - CreateCallback
---

# SILO_MONITOR_CREATE_CALLBACK callback function


## -description

This is callback is invoked when a new silo is created.

## -parameters

### -param Silo 

[in]
The silo that was created.

## -returns

The NT code returned by the operation.

