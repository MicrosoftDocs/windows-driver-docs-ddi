---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_PASS
title: PFND3D12DDI_BEGIN_PASS (d3d12umddi.h)
description: The driver is notified that the app has started of a pass of consistent workloads.
tech.root: display
ms.assetid: 05d0f76c-4a82-433c-9d97-a4fb2c4b4e1a
ms.date: 11/28/2018
keywords: ["PFND3D12DDI_BEGIN_PASS callback function"]
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_BEGIN_PASS"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver: D3D12DDI_SUPPORTED_0020
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
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_BEGIN_PASS
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_BEGIN_PASS callback function

## -description

The driver is notified that the app has started of a pass of consistent workloads. When the driver is notified that an app pass has started, the driver either records observations or uses optimizations that have been discovered.


## -prototype

```
//Declaration

PFND3D12DDI_BEGIN_PASS Pfnd3d12ddiBeginPass; 

// Definition

VOID Pfnd3d12ddiBeginPass 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HPASS Arg2
	D3D12DDI_PASS_FLAGS PassFlags
)
{...}

```

## -parameters

### -param Arg1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

A handle to the pass that was created by the app.

### -param PassFlags

A flag to indicate what the driver should do when an app starts a pass.

## -remarks

This callback is used as part of a test to see if drivers can find perf wins from being told when apps are repeating "passes" of consistent workloads. The app instructs the driver to observe how some passes run and gives the driver a chance to make optimizations for future runs of the same pass. The contents of a "pass" can be anything - it is up to the app to be relatively consistent in the overall performance characteristics of a pass.


## -see-also
