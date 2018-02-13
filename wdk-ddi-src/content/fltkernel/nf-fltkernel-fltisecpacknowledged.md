---
UID: NF:fltkernel.FltIsEcpAcknowledged
title: FltIsEcpAcknowledged function
author: windows-driver-content
description: The FltIsEcpAcknowledged routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged.
old-location: ifsk\fltisecpacknowledged.htm
old-project: ifsk
ms.assetid: ae4f4dfd-2a1d-4116-b56c-f7250697cf9e
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltkernel/FltIsEcpAcknowledged, ifsk.fltisecpacknowledged, FltIsEcpAcknowledged, FltApiRef_e_to_o_a5a70461-2108-4e8f-a01b-0fec773f6010.xml, FltIsEcpAcknowledged routine [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	FltMgr.sys
apiname:
-	FltIsEcpAcknowledged
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsEcpAcknowledged function


## -description


The <b>FltIsEcpAcknowledged</b> routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged.


## -syntax


````
BOOLEAN FltIsEcpAcknowledged(
  _In_ PFLT_FILTER Filter,
  _In_ PVOID       EcpContext
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

Pointer to the ECP to test for acknowledgment.


## -returns



The routine returns <b>TRUE</b> if the ECP was marked as acknowledged and <b>FALSE</b> otherwise.




## -remarks



To mark an ECP as acknowledged, use the <a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a> routine.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltisecpfromusermode.md">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsEcpAcknowledged routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

