---
UID: NF:wpprecorder.WppRecorderGetTriageInfo
title: WppRecorderGetTriageInfo macro
author: windows-driver-content
description: The WppRecorderGetTriageInfo.
old-location: devtest\wpprecordergettriageinfo.htm
old-project: devtest
ms.assetid: D2790496-1F86-4EF0-8AFE-77AC0C89EE05
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WppRecorderGetTriageInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wpprecorder.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WppRecorderGetTriageInfo
req.alt-loc: wpprecorder.h
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

# WppRecorderGetTriageInfo macro



## -description
The <b>WppRecorderGetTriageInfo</b> method 



## -syntax

````
NTSTATUS WppRecorderGetTriageInfo(
  _Out_ PWPP_TRIAGE_INFO WppTriageInfo
);
````


## -parameters

### -param WppTriageInfo [out]

Pointer to a <a href="..\wpprecorder\ns-wpprecorder-_wpp_triage_info.md">WPP_TRIAGE_INFO</a> structure.


## -remarks
