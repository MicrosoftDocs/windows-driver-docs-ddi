---
UID: NF:wpprecorder.imp_WppRecorderLinkCounters
title: imp_WppRecorderLinkCounters function (wpprecorder.h)
description: The WppRecorderLinkCounters.
old-location: devtest\wpprecorderlinkcounters.htm
tech.root: devtest
ms.assetid: D8FF1E87-EB3E-491E-9649-076376C272B3
ms.date: 02/23/2018
ms.keywords: WppRecorderLinkCounters, devtest.wpprecorderlinkcounters, imp_WppRecorderLinkCounters, imp_WppRecorderLinkCounters function [Driver Development Tools], wpprecorder/imp_WppRecorderLinkCounters
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
-	wpprecorder.h
api_name:
-	imp_WppRecorderLinkCounters
product:
- Windows
targetos: Windows
req.typenames: 
---

# imp_WppRecorderLinkCounters function


## -description


The <b>WppRecorderLinkCounters</b> method  uses a sequence number to merge logs captured in different buffers by a driver.


## -parameters




### -param WppCb

<p>ID of the counter whose current value is to be read.</p>


### -param CounterOwner [in]

ID of the counter whose current value is to be read.


## -returns



Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> values



