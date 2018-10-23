---
UID: NF:ntifs.FsRtlAcknowledgeEcp
title: FsRtlAcknowledgeEcp function
author: windows-driver-content
description: The FsRtlAcknowledgeEcp routine marks an extra create parameter (ECP) context structure as acknowledged.
old-location: ifsk\fsrtlacknowledgeecp.htm
tech.root: ifsk
ms.assetid: 1f91c2ef-300d-43f5-8d2c-d4f2fd326915
ms.date: 04/16/2018
ms.keywords: FsRtlAcknowledgeEcp, FsRtlAcknowledgeEcp routine [Installable File System Drivers], fsrtlref_2c3b8577-e61e-4ff3-9443-b3838077d762.xml, ifsk.fsrtlacknowledgeecp, ntifs/FsRtlAcknowledgeEcp
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	FsRtlAcknowledgeEcp
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlAcknowledgeEcp function


## -description


The <b>FsRtlAcknowledgeEcp</b> routine marks an extra create parameter (ECP) context structure as acknowledged.


## -parameters




### -param EcpContext [in]

A pointer to the ECP to mark as acknowledged.


## -returns



None




## -remarks



When <b>FsRtlAcknowledgeEcp</b> marks an ECP as acknowledged, it could indicate   whether the ECP has been looked at, used, processed, or any other condition of the ECP.  

You can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a> routine to determine if a particular ECP has been marked as acknowledged.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>
 

 

