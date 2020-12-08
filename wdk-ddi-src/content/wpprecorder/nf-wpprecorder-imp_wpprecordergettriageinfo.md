---
UID: NF:wpprecorder.imp_WppRecorderGetTriageInfo
title: imp_WppRecorderGetTriageInfo function (wpprecorder.h)
description: The WppRecorderGetTriageInfo.
old-location: devtest\wpprecordergettriageinfo.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["imp_WppRecorderGetTriageInfo function"]
ms.keywords: devtest.wpprecordergettriageinfo, imp_WppRecorderGetTriageInfo, imp_WppRecorderGetTriageInfo function [Driver Development Tools], wpprecorder/imp_WppRecorderGetTriageInfo
req.header: wpprecorder.h
req.include-header: 
req.target-type: Desktop
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
 - imp_WppRecorderGetTriageInfo
 - wpprecorder/imp_WppRecorderGetTriageInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wpprecorder.h
api_name:
 - imp_WppRecorderGetTriageInfo
---

# imp_WppRecorderGetTriageInfo function


## -description

The <b>WppRecorderGetTriageInfo</b> method

## -parameters

### -param WppCb

<p>Pointer to a <a href="/windows-hardware/drivers/ddi/wpprecorder/ns-wpprecorder-_wpp_triage_info"><b>WPP_TRIAGE_INFO</b></a> structure.</p>

### -param WppTriageInfo 

[out]
Pointer to a <a href="/windows-hardware/drivers/ddi/wpprecorder/ns-wpprecorder-_wpp_triage_info">WPP_TRIAGE_INFO</a> structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> values
