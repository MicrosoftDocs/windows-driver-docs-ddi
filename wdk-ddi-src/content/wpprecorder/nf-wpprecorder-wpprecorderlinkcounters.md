---
UID: NF:wpprecorder.WppRecorderLinkCounters
title: WppRecorderLinkCounters macro
author: windows-driver-content
description: The WppRecorderLinkCounters.
old-location: devtest\wpprecorderlinkcounters.htm
old-project: devtest
ms.assetid: D8FF1E87-EB3E-491E-9649-076376C272B3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WppRecorderLinkCounters
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
req.alt-api: WppRecorderLinkCounters
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

# WppRecorderLinkCounters macro



## -description
The <b>WppRecorderLinkCounters</b> method  uses a sequence number to merge logs captured in different buffers by a driver.



## -syntax

````
NTSTATUS WppRecorderLinkCounters(
  _In_ WPP_RECORDER_COUNTER CounterOwner
);
````


## -parameters

### -param CounterOwner [in]

ID of the counter whose current value is to be read.


## -remarks
