---
UID: NF:ntddstor.DeviceDsmGetOutputBlockLength
title: DeviceDsmGetOutputBlockLength function
author: windows-driver-content
description: The DeviceDsmGetOutputBlockLength function gets the length, in bytes, of an output block.
ms.assetid: 57512e92-810a-423e-98c0-be892cc81c88
ms.date: 04/11/2018
ms.topic: function
ms.keywords: DeviceDsmGetOutputBlockLength
req.header: ntddstor.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1803
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
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	DeviceDsmGetOutputBlockLength
product:
-	Windows
targetos: Windows

---

# DeviceDsmGetOutputBlockLength function


## -description

The **DeviceDsmGetOutputBlockLength** function gets the length, in bytes, of an output block.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains output block alignment and length information.

### -param OutputLength

The length of the output.

## -returns

Returns the length, in bytes, of the output block.

## -remarks

## -see-also
