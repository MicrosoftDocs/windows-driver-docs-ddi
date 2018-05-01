---
UID: NF:wpprecorder.imp_WppRecorderGetTriageInfo
title: imp_WppRecorderGetTriageInfo function
author: windows-driver-content
description: The WppRecorderGetTriageInfo.
old-location: devtest\wpprecordergettriageinfo.htm
old-project: devtest
ms.assetid: D2790496-1F86-4EF0-8AFE-77AC0C89EE05
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: devtest.wpprecordergettriageinfo, imp_WppRecorderGetTriageInfo, imp_WppRecorderGetTriageInfo function [Driver Development Tools], wpprecorder/imp_WppRecorderGetTriageInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wpprecorder.h
api_name:
-	imp_WppRecorderGetTriageInfo
product: Windows
targetos: Windows
req.typenames: 
---

# imp_WppRecorderGetTriageInfo function


## -description


The <b>WppRecorderGetTriageInfo</b> method 


## -parameters




### -param WppCb

TBD


### -param WppTriageInfo [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn895242">WPP_TRIAGE_INFO</a> structure.


## -returns



Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> values



