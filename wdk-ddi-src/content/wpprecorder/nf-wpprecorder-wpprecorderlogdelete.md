---
UID: NF:wpprecorder.WppRecorderLogDelete
title: WppRecorderLogDelete macro
author: windows-driver-content
description: The WppRecorderLogDelete method deletes the specified recorder log.
old-location: devtest\wpprecorderlogdelete.htm
old-project: devtest
ms.assetid: AEE10756-7301-4B55-82A5-27CA595854EA
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WppRecorderLogDelete
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
req.alt-api: WppRecorderLogDelete
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

# WppRecorderLogDelete macro



## -description
The <a href="..\wpprecorder\nf-wpprecorder-wpprecorderlogdelete.md">WppRecorderLogDelete</a> method deletes the specified recorder log.



## -syntax

````
NTSTATUS WppRecorderLogDelete(
   NULL RecorderLog
);
````


## -parameters

### -param RecorderLog 

Handle to the recorder log to delete.


## -remarks
When a thread enters this function, no threads can subsequently  log to this buffer.</p>