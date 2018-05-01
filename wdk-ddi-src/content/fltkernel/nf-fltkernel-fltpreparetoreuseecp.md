---
UID: NF:fltkernel.FltPrepareToReuseEcp
title: FltPrepareToReuseEcp function
author: windows-driver-content
description: The FltPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse.
old-location: ifsk\fltpreparetoreuseecp.htm
old-project: ifsk
ms.assetid: E08E2ED1-047B-4190-8A54-79ECC75E860F
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltPrepareToReuseEcp, FltPrepareToReuseEcp routine [Installable File System Drivers], fltkernel/FltPrepareToReuseEcp, ifsk.fltpreparetoreuseecp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltPrepareToReuseEcp
product: Windows
targetos: Windows
req.typenames: 
---

# FltPrepareToReuseEcp function


## -description


The <b>FltPrepareToReuseEcp</b> routine resets an extra create parameter (ECP) context structure,  which prepares  it for reuse.


## -parameters




### -param Filter [in]

An opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

A pointer to the ECP to prepare for reuse.


## -returns



None.




## -remarks



The <b>FltPrepareToReuseEcp</b> allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a> to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse a previously acknowledged ECP, such as in processing a reparse, a driver can use <b>FltPrepareToReuseEcp</b> to clear the acknowledged state from the ECP before sending it in another create request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/b4cc03e9-225f-491f-97df-064fdedc8182">FltlInsertExtraCreateParameter</a>
 

 

