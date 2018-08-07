---
UID: NF:ntddstor.DeviceDsmGetOutputLength
title: DeviceDsmGetOutputLength function
author: windows-driver-content
description: The DeviceDsmGetOutputLength function gets the length, in bytes, of a data set management output operation.
ms.assetid: deb9e6b6-d744-4c3a-a6f4-d1b452401a08
ms.author: windowsdriverdev
ms.date: 04/11/2018
ms.topic: function
ms.keywords: DeviceDsmGetOutputLength
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
-	DeviceDsmGetOutputLength
product:
-	Windows
targetos: Windows

---

# DeviceDsmGetOutputLength function


## -description

The **DeviceDsmGetOutputLength** function gets the length, in bytes, of a data set management output operation.

## -parameters

### -param Definition

A pointer to a DEVICE_DSM_DEFINITION structure that contains output block alignment and length information.

### -param OutputBlockLength

The length of the output block.

## -returns

Returns the number of bytes in the output: the length of a [**DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT**](ns-ntddstor-_device_manage_data_set_attributes_output.md) structure and the length of the output block.

## -remarks

## -see-also