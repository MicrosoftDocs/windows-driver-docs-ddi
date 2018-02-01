---
UID: NF:ntifs.FsRtlFreeExtraCreateParameterList
title: FsRtlFreeExtraCreateParameterList function
author: windows-driver-content
description: The FsRtlFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure.
old-location: ifsk\fsrtlfreeextracreateparameterlist.htm
old-project: ifsk
ms.assetid: 0d2f1204-0874-4ede-9931-be6f2dbc3c47
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fsrtlfreeextracreateparameterlist, fsrtlref_909d50be-4f8d-47dc-ad00-03d3f9eb4533.xml, FsRtlFreeExtraCreateParameterList, FsRtlFreeExtraCreateParameterList routine [Installable File System Drivers], ntifs/FsRtlFreeExtraCreateParameterList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlFreeExtraCreateParameterList routine is available starting with Windows Vista.
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
-	FsRtlFreeExtraCreateParameterList
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlFreeExtraCreateParameterList function


## -description


The <b>FsRtlFreeExtraCreateParameterList</b> routine frees an extra create parameter (ECP) list structure.


## -syntax


````
VOID FsRtlFreeExtraCreateParameterList(
  _In_ PECP_LIST EcpList
);
````


## -parameters




### -param EcpList [in]

Pointer to the ECP list structure to be freed.


## -returns


None



## -remarks


<b>FsRtlFreeExtraCreateParameterList</b> frees an ECP list structure including any list elements, if they exist.  



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlFreeExtraCreateParameterList routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

