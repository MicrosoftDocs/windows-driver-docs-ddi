---
UID: NF:wpprecorder.WppRecorderLogSetIdentifier
title: WppRecorderLogSetIdentifier macro (wpprecorder.h)
description: The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log.
old-location: devtest\wpprecorderlogsetidentifier.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["WppRecorderLogSetIdentifier macro"]
ms.keywords: WppRecorderLogSetIdentifier, devtest.wpprecorderlogsetidentifier, imp_WppRecorderLogSetIdentifier, imp_WppRecorderLogSetIdentifier function [Driver Development Tools], wpprecorder/imp_WppRecorderLogSetIdentifier
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
 - WppRecorderLogSetIdentifier
 - wpprecorder/WppRecorderLogSetIdentifier
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - WppRecorderLogSetIdentifier
---

# WppRecorderLogSetIdentifier macro


## -description

The <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogsetidentifier">WppRecorderLogSetIdentifier</a> method sets a string identifier for the recorder log.

## -parameters

### -param RecorderLog

A recorder log handle returned in a previous call to WppRecorderLogCreate.

### -param LogIdentifier

A string identifier to set.

## -remarks

Do not call <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogsetidentifier">WppRecorderLogSetIdentifier</a> on the default log handle returned by <a href="/previous-versions/windows/hardware/previsioning-framework/dn895240(v=vs.85)">WppRecorderLogGetDefault</a>.

