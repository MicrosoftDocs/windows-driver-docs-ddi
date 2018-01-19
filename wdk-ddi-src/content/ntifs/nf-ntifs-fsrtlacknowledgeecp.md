---
UID: NF:ntifs.FsRtlAcknowledgeEcp
title: FsRtlAcknowledgeEcp function
author: windows-driver-content
description: The FsRtlAcknowledgeEcp routine marks an extra create parameter (ECP) context structure as acknowledged.
old-location: ifsk\fsrtlacknowledgeecp.htm
old-project: ifsk
ms.assetid: 1f91c2ef-300d-43f5-8d2c-d4f2fd326915
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlAcknowledgeEcp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlAcknowledgeEcp
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlAcknowledgeEcp function



## -description
The <b>FsRtlAcknowledgeEcp</b> routine marks an extra create parameter (ECP) context structure as acknowledged.



## -syntax

````
VOID FsRtlAcknowledgeEcp(
  _In_ PVOID EcpContext
);
````


## -parameters

### -param EcpContext [in]

A pointer to the ECP to mark as acknowledged.


## -returns
None


## -remarks
When <b>FsRtlAcknowledgeEcp</b> marks an ECP as acknowledged, it could indicate   whether the ECP has been looked at, used, processed, or any other condition of the ECP.  

You can use the <a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a> routine to determine if a particular ECP has been marked as acknowledged.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltisecpfromusermode.md">FltIsEcpFromUserMode</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAcknowledgeEcp routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

