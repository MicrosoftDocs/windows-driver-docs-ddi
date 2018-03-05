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


## -syntax


````
VOID FsRtlPrepareToReuseEcp(
  _In_ PVOID EcpContext
);
````


## -parameters




### -param EcpContext [in]

A pointer to the ECP to prepare for reuse.


## -returns



None.




## -remarks



The <b>FsRtlPrepareToReuseEcp</b> allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses <a href="..\ntifs\nf-ntifs-fsrtlacknowledgeecp.md">FsRtlAcknowledgeEcp</a> to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse an previously acknowledged ECP, such as in processing a reparse, a driver can use <b>FsRtlPrepareToReuseEcp</b> to clear the acknowledged state from the ECP before sending it in another create request.

Within a file system minifilter driver, use <a href="..\fltkernel\nf-fltkernel-fltpreparetoreuseecp.md">FltPrepareToReuseEcp</a> to reuse an ECP.




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlremoveextracreateparameter.md">FsRtlRemoveExtraCreateParameter</a>



<a href="..\ntifs\nf-ntifs-fsrtlisecpacknowledged.md">FsRtlIsEcpAcknowledged</a>



<a href="..\fltkernel\nf-fltkernel-fltpreparetoreuseecp.md">FltPrepareToReuseEcp</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertextracreateparameter.md">FsRtlInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlPrepareToReuseEcp routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

