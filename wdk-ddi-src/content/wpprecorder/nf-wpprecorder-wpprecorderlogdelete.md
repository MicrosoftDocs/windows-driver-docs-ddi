---
UID: NF:wpprecorder.WppRecorderLogDelete
title: WppRecorderLogDelete macro (wpprecorder.h)
description: The WppRecorderLogDelete method deletes the specified recorder log.
old-location: devtest\wpprecorderlogdelete.htm
tech.root: devtest
ms.assetid: AEE10756-7301-4B55-82A5-27CA595854EA
ms.date: 02/23/2018
keywords: ["WppRecorderLogDelete macro"]
ms.keywords: WppRecorderLogDelete, devtest.wpprecorderlogdelete, imp_WppRecorderLogDelete, imp_WppRecorderLogDelete function [Driver Development Tools], wpprecorder/imp_WppRecorderLogDelete
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
 - WppRecorderLogDelete
 - wpprecorder/WppRecorderLogDelete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - imp_WppRecorderLogDelete
---

# WppRecorderLogDelete macro


## -description

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderlogdelete">WppRecorderLogDelete</a> method deletes the specified recorder log.

## -parameters

### -param RecorderLog

Handle to the recorder log to delete.

## -remarks

When a thread enters this function, no threads can subsequently  log to this buffer.

