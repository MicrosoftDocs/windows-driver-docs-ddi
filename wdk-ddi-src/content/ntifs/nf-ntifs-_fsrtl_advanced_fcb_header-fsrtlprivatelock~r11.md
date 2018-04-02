---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPrivateLock~r11
title: FsRtlPrivateLock function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\fsrtlprivatelock.htm
old-project: ifsk
ms.assetid: c0f6b5bd-991c-403c-9bda-82960b356ca9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlPrivateLock, FsRtlPrivateLock function [Installable File System Drivers], fsrtlref_950e4ca4-4e7f-4158-8e1e-083af825488d.xml, ifsk.fsrtlprivatelock, ntifs/FsRtlPrivateLock
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlPrivateLock
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlPrivateLock function


## -description


The <b>FsRtlPrivateLock</b> routine is obsolete, but is exported to support existing driver binaries. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545940">FsRtlFastLock</a> instead.


## -parameters




### -param FileLock

TBD


### -param FileObject

TBD


### -param FileOffset

TBD


### -param Length

TBD


### -param ProcessId

TBD


### -param Key

TBD


### -param FailImmediately

TBD


### -param ExclusiveLock

TBD


### -param Iosb

TBD


### -param Irp

TBD


### -param Context

TBD


### -param AlreadySynchronized

TBD





