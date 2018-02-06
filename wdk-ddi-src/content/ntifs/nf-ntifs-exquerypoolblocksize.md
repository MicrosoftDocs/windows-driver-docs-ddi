---
UID: NF:ntifs.ExQueryPoolBlockSize
title: ExQueryPoolBlockSize function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\exquerypoolblocksize.htm
old-project: ifsk
ms.assetid: 0be3f5da-3fe6-45a2-b44a-b1634d74ede3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: exref_c8686b81-2d69-4bbf-a1fb-143574579cff.xml, ExQueryPoolBlockSize, ExQueryPoolBlockSize function [Installable File System Drivers], ifsk.exquerypoolblocksize, ntifs/ExQueryPoolBlockSize
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
-	ExQueryPoolBlockSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# ExQueryPoolBlockSize function


## -description


<b>ExQueryPoolBlockSize</b> is obsolete and has never been documented. This routine is exported only to support a small number of legacy drivers. Also, if you call it in Microsoft Windows 2000 and the block is in special pool, the system will crash. Do not use this routine in your driver. 


## -syntax


````
  ExQueryPoolBlockSize(
    
);
````


## -parameters




### -param PoolBlock

TBD


### -param QuotaCharged

TBD





