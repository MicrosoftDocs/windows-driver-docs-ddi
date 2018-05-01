---
UID: NF:ntifs.FsRtlInitializeExtraCreateParameterList
title: FsRtlInitializeExtraCreateParameterList function
author: windows-driver-content
description: The FsRtlInitializeExtraCreateParameterList routine initializes an extra create parameter (ECP) context structure list.
old-location: ifsk\fsrtlinitializeextracreateparameterlist.htm
old-project: ifsk
ms.assetid: 79e56363-1098-42bb-8e6a-c4b4c76e7e7c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlInitializeExtraCreateParameterList, FsRtlInitializeExtraCreateParameterList routine [Installable File System Drivers], fsrtlref_785d3f11-f568-491e-9cdb-abba70ae3eeb.xml, ifsk.fsrtlinitializeextracreateparameterlist, ntifs/FsRtlInitializeExtraCreateParameterList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitializeExtraCreateParameterList routine is available starting with Windows 7.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlInitializeExtraCreateParameterList
product: Windows
targetos: Windows
req.typenames: 
---

# FsRtlInitializeExtraCreateParameterList function


## -description


The <b>FsRtlInitializeExtraCreateParameterList</b> routine initializes an extra create parameter (ECP) context structure list. 


## -parameters




### -param EcpList [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> structure to initialize. 


## -returns



<b>FsRtlInitializeExtraCreateParameterList</b> returns STATUS_SUCCESS if it successfully initialized the given <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> structure, and returns an error if it did not. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
 

 

