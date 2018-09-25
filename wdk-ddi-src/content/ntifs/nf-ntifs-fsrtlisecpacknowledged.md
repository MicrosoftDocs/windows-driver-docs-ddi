---
UID: NF:ntifs.FsRtlIsEcpAcknowledged
title: FsRtlIsEcpAcknowledged function
author: windows-driver-content
description: The FsRtlIsEcpAcknowledged routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged.
old-location: ifsk\fsrtlisecpacknowledged.htm
tech.root: ifsk
ms.assetid: ee2f06f6-3295-4a92-b232-daf66ec6195a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FsRtlIsEcpAcknowledged, FsRtlIsEcpAcknowledged routine [Installable File System Drivers], fsrtlref_5e05018f-5f4a-41e1-a05a-93ab636012e1.xml, ifsk.fsrtlisecpacknowledged, ntifs/FsRtlIsEcpAcknowledged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlIsEcpAcknowledged routine is available starting with Windows Vista.
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
-	FsRtlIsEcpAcknowledged
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsEcpAcknowledged function


## -description


The <b>FsRtlIsEcpAcknowledged</b> routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged.


## -parameters




### -param EcpContext [in]

Pointer to the ECP context structure to test for acknowledgment.


## -returns



The <b>FsRtlIsEcpAcknowledged </b>routine returns <b>TRUE</b> if the ECP was marked as acknowledged and <b>FALSE</b> otherwise.




## -remarks



To mark an ECP context structure as acknowledged, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>
 

 

