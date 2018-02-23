---
UID: NF:ntifs.KeAttachProcess
title: KeAttachProcess function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\keattachprocess.htm
old-project: ifsk
ms.assetid: 1261e65b-c862-4c99-89ed-c222b017272a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.keattachprocess, ntifs/KeAttachProcess, KeAttachProcess function [Installable File System Drivers], KeAttachProcess, keref_ee648ca5-3597-4caf-9a8c-5e6cc4543964.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	KeAttachProcess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeAttachProcess function


## -description


The <b>KeAttachProcess</b> routine is exported to support existing driver binaries and is obsolete. Use <a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a> instead.


## -syntax


````
  KeAttachProcess(
    
);
````


## -parameters




### -param Process

TBD





