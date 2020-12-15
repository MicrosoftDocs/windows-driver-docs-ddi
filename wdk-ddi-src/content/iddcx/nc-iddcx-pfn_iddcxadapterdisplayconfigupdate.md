---
UID: NC:iddcx.PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
title: PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
author: windows-driver-content
description: PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE is a pointer to an OS callback function that updates the display configuration for the remote session.
tech.root: display
ms.author: windowsdriverdev
ms.date: 09/28/2020
keywords: ["PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback pointer"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
 - iddcx/PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
product:
 - Windows
dev_langs:
 - c++
---

# PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback function

## -description

**PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE** is a pointer to an OS callback function that updates the display configuration for the remote session.

## -parameters

### -param DriverGlobals

[in] Pointer to an [**IDD_DRIVER_GLOBALS**](./ns-iddcx-idd_driver_globals.md) structure containing system-defined per-driver data.

### -param AdapterObject

[in] The adapter object of the remote adapter that the display configuration is specified for.

### -param pInArgs

[in] Input arguments.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS Values error code.

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md).

## -see-also

[**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md)
