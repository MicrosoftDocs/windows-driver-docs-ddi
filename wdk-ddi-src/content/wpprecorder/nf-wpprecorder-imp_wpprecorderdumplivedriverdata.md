---
UID: NF:wpprecorder.imp_WppRecorderDumpLiveDriverData
title: imp_WppRecorderDumpLiveDriverData function
author: windows-driver-content
description: The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log.
old-location: devtest\wpprecorderdumplivedriverdata.htm
tech.root: devtest
ms.assetid: FE3DE2A8-8EE5-4F34-BEE6-731987E5F5BD
ms.date: 2/23/2018
ms.keywords: WppRecorderDumpLiveDriverData, devtest.wpprecorderdumplivedriverdata, imp_WppRecorderDumpLiveDriverData, imp_WppRecorderDumpLiveDriverData function [Driver Development Tools], wpprecorder/imp_WppRecorderDumpLiveDriverData
ms.topic: function
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wpprecorder.h
api_name:
-	imp_WppRecorderDumpLiveDriverData
product:
- Windows
targetos: Windows
req.typenames: 
---

# imp_WppRecorderDumpLiveDriverData function


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/dn914612">WppRecorderDumpLiveDriverData</a> method gets the buffer associated with the specified Inflight Trace Recorder log.


## -parameters




### -param WppCb

<p>Pointer to the buffer that was allocated by WppRecorderLogCreate.</p>


### -param OutBuffer

Pointer to the buffer that was allocated by WppRecorderLogCreate.


### -param OutBufferLength

Pointer to a ULONG that contains the size of the output buffer pointed to by OutBuffer.


### -param Guid

Pointer to the WPP controller GUID that identifies the driver data.


## -returns



Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> values



