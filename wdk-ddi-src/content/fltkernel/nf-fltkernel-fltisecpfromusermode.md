---
UID: NF:fltkernel.FltIsEcpFromUserMode
title: FltIsEcpFromUserMode function
author: windows-driver-content
description: The FltIsEcpFromUserMode routine is used to determine if an extra create parameter context structure (ECP) originated from user mode.
old-location: ifsk\fltisecpfromusermode.htm
old-project: ifsk
ms.assetid: d00cb2b1-b579-43c9-9e4d-cbdefd8a343a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, F, FltApiRef_e_to_o_ea63cca7-3efb-4b45-b075-7efbc8138f88.xml, FltIsEcpFromUserMode, FltIsEcpFromUserMode routine [Installable File System Drivers], I, M, U, c, d, e, fltkernel/FltIsEcpFromUserMode, ifsk.fltisecpfromusermode, l, m, o, p, r, s, t"
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
-	FltIsEcpFromUserMode
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltIsEcpFromUserMode function


## -description


The <b>FltIsEcpFromUserMode </b>routine is used to determine if an extra create parameter context structure (ECP) originated from user mode.


## -syntax


````
BOOLEAN FltIsEcpFromUserMode(
  _In_ PFLT_FILTER Filter,
  _In_ PVOID       EcpContext
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.


### -param EcpContext [in]

Pointer to the ECP to test.


## -returns



The routine returns <b>TRUE</b> if the ECP originated in user mode and <b>FALSE</b> if the ECP originated in kernel mode.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltIsEcpFromUserMode routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

