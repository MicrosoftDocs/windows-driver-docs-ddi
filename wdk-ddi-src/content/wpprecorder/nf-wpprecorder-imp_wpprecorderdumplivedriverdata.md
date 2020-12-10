---
UID: NF:wpprecorder.imp_WppRecorderDumpLiveDriverData
title: imp_WppRecorderDumpLiveDriverData function (wpprecorder.h)
description: The WppRecorderDumpLiveDriverData method gets the buffer associated with the specified Inflight Trace Recorder log.
old-location: devtest\wpprecorderdumplivedriverdata.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["imp_WppRecorderDumpLiveDriverData function"]
ms.keywords: WppRecorderDumpLiveDriverData, devtest.wpprecorderdumplivedriverdata, imp_WppRecorderDumpLiveDriverData, imp_WppRecorderDumpLiveDriverData function [Driver Development Tools], wpprecorder/imp_WppRecorderDumpLiveDriverData
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
targetos: Windows
req.typenames: 
f1_keywords:
 - imp_WppRecorderDumpLiveDriverData
 - wpprecorder/imp_WppRecorderDumpLiveDriverData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - imp_WppRecorderDumpLiveDriverData
---

# imp_WppRecorderDumpLiveDriverData function


## -description

The <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderdumplivedriverdata">WppRecorderDumpLiveDriverData</a> method gets the buffer associated with the specified Inflight Trace Recorder log.

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

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> values
