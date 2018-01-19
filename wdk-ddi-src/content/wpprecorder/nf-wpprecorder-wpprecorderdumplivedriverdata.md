---
UID: NF:wpprecorder.WppRecorderDumpLiveDriverData
title: WppRecorderDumpLiveDriverData macro
author: windows-driver-content
description: The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log.
old-location: devtest\wpprecorderdumplivedriverdata.htm
old-project: devtest
ms.assetid: FE3DE2A8-8EE5-4F34-BEE6-731987E5F5BD
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WppRecorderDumpLiveDriverData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WppRecorderDumpLiveDriverData
req.alt-loc: Wpprecorder.h
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
req.typenames: *PWNODE_HEADER, WNODE_HEADER
req.product: Windows 10 or later.
---

# WppRecorderDumpLiveDriverData macro



## -description
The <a href="..\wpprecorder\nf-wpprecorder-wpprecorderdumplivedriverdata.md">WppRecorderDumpLiveDriverData</a> method gets the buffer associated with the specified Inflight Trace Recorder log.



## -syntax

````
NTSTATUS WppRecorderDumpLiveDriverData(
   NULL OutBuffer,
   NULL OutBufferLength,
   NULL Guid
);
````


## -parameters

### -param OutBuffer 

Pointer to the buffer that was allocated by WppRecorderLogCreate.


### -param OutBufferLength 

Pointer to a ULONG that contains the size of the output buffer pointed to by OutBuffer.


### -param Guid 

Pointer to the WPP controller GUID that identifies the driver data.


## -remarks
