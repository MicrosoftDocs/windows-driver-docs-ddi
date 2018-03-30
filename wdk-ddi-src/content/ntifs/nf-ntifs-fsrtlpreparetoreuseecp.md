---
UID: NF:ntifs.FsRtlPrepareToReuseEcp
title: FsRtlPrepareToReuseEcp function
author: windows-driver-content
description: The FsRtlPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse.
old-location: ifsk\fsrtlpreparetoreuseecp.htm
old-project: ifsk
ms.assetid: 88967BD6-C633-40D0-BE4F-2B08494EA5B0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlPrepareToReuseEcp, FsRtlPrepareToReuseEcp routine [Installable File System Drivers], ifsk.fsrtlpreparetoreuseecp, ntifs/FsRtlPrepareToReuseEcp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	FsRtlPrepareToReuseEcp
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlPrepareToReuseEcp function


## -description


The <b>FsRtlPrepareToReuseEcp</b> routine resets an extra create parameter (ECP) context structure, which  prepares it for reuse.


## -parameters




### -param EcpContext [in]

A pointer to the ECP to prepare for reuse.


## -returns



None.




## -remarks



The <b>FsRtlPrepareToReuseEcp</b> allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff545574">FsRtlAcknowledgeEcp</a> to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse an previously acknowledged ECP, such as in processing a reparse, a driver can use <b>FsRtlPrepareToReuseEcp</b> to clear the acknowledged state from the ECP before sending it in another create request.

Within a file system minifilter driver, use <a href="https://msdn.microsoft.com/library/windows/hardware/hh451026">FltPrepareToReuseEcp</a> to reuse an ECP.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451026">FltPrepareToReuseEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546179">FsRtlInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546808">FsRtlIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547203">FsRtlRemoveExtraCreateParameter</a>
 

 

