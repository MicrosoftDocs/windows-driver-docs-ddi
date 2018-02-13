---
UID: NF:ntifs.FsRtlIsEcpAcknowledged
title: FsRtlIsEcpAcknowledged function
author: windows-driver-content
description: The FsRtlIsEcpAcknowledged routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged.
old-location: ifsk\fsrtlisecpacknowledged.htm
old-project: ifsk
ms.assetid: ee2f06f6-3295-4a92-b232-daf66ec6195a
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.fsrtlisecpacknowledged, FsRtlIsEcpAcknowledged, fsrtlref_5e05018f-5f4a-41e1-a05a-93ab636012e1.xml, FsRtlIsEcpAcknowledged routine [Installable File System Drivers], ntifs/FsRtlIsEcpAcknowledged
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlIsEcpAcknowledged
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsEcpAcknowledged function


## -description


The <b>FsRtlIsEcpAcknowledged</b> routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged.


## -syntax


````
BOOLEAN FsRtlIsEcpAcknowledged(
  _In_ PVOID EcpContext
);
````


## -parameters




### -param EcpContext [in]

Pointer to the ECP context structure to test for acknowledgment.


## -returns



The <b>FsRtlIsEcpAcknowledged </b>routine returns <b>TRUE</b> if the ECP was marked as acknowledged and <b>FALSE</b> otherwise.




## -remarks



To mark an ECP context structure as acknowledged, use the <a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a> routine.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltisecpfromusermode.md">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIsEcpAcknowledged routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

