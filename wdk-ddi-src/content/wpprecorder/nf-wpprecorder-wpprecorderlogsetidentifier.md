---
UID: NF:wpprecorder.WppRecorderLogSetIdentifier
title: WppRecorderLogSetIdentifier macro
author: windows-driver-content
description: The WppRecorderLogSetIdentifier method sets a string identifier for the recorder log.
old-location: devtest\wpprecorderlogsetidentifier.htm
old-project: devtest
ms.assetid: E2687B3C-2BCF-4764-99E0-4495296F14C4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: WppRecorderLogSetIdentifier, devtest.wpprecorderlogsetidentifier, imp_WppRecorderLogSetIdentifier, imp_WppRecorderLogSetIdentifier function [Driver Development Tools], wpprecorder/imp_WppRecorderLogSetIdentifier
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
-	imp_WppRecorderLogSetIdentifier
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# WppRecorderLogSetIdentifier macro


## -description


The <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogsetidentifier.md">WppRecorderLogSetIdentifier</a> method sets a string identifier for the recorder log.


## -syntax


````
NTSTATUS imp_WppRecorderLogSetIdentifier(
   NULL RecorderLog,
   NULL LogIdentifier
);
````


## -parameters




### -param RecorderLog

A recorder log handle returned in a previous call to WppRecorderLogCreate.


### -param LogIdentifier

A string identifier to set.


## -remarks



Do not call <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogsetidentifier.md">WppRecorderLogSetIdentifier</a> on the default log handle returned by <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderloggetdefault.md">WppRecorderLogGetDefault</a>.



