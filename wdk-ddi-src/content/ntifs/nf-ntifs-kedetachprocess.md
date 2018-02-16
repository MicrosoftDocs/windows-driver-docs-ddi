---
UID: NF:ntifs.KeDetachProcess
title: KeDetachProcess function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\kedetachprocess.htm
old-project: ifsk
ms.assetid: 25cb0b53-f5b2-460a-bcab-56196f568d12
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: KeDetachProcess function [Installable File System Drivers], keref_0038ac90-7d97-45db-9a0d-028238af943d.xml, ifsk.kedetachprocess, ntifs/KeDetachProcess, KeDetachProcess
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
-	KeDetachProcess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeDetachProcess function


## -description


The <b>KeDetachProcess</b> routine is exported to support existing driver binaries and is obsolete. Use <a href="..\ntifs\nf-ntifs-keunstackdetachprocess.md">KeUnstackDetachProcess</a> instead.


## -syntax


````
  KeDetachProcess(
    
);
````


## -parameters







