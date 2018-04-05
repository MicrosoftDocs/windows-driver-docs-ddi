---
UID: NF:fltkernel.FltIsEcpAcknowledged
title: FltIsEcpAcknowledged function
author: windows-driver-content
description: The FltIsEcpAcknowledged routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged.
old-location: ifsk\fltisecpacknowledged.htm
old-project: ifsk
ms.assetid: ae4f4dfd-2a1d-4116-b56c-f7250697cf9e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_a5a70461-2108-4e8f-a01b-0fec773f6010.xml, FltIsEcpAcknowledged, FltIsEcpAcknowledged routine [Installable File System Drivers], fltkernel/FltIsEcpAcknowledged, ifsk.fltisecpacknowledged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.dll: FltMgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	FltMgr.sys
api_name:
-	FltIsEcpAcknowledged
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsEcpAcknowledged function


## -description


The <b>FltIsEcpAcknowledged</b> routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged.


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

Pointer to the ECP to test for acknowledgment.


## -returns



The routine returns <b>TRUE</b> if the ECP was marked as acknowledged and <b>FALSE</b> otherwise.




## -remarks



To mark an ECP as acknowledged, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>
 

 

