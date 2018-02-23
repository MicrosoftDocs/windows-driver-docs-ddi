---
UID: NF:ntddk.RtlSubtreeSuccessor
title: RtlSubtreeSuccessor function
author: windows-driver-content
description: The RtlSubtreeSuccessor routine returns a pointer to the successor of the specified node within the subtree that is rooted at that node.
old-location: ifsk\rtlsubtreesuccessor.htm
old-project: ifsk
ms.assetid: de592c2a-6f52-48ef-b2ee-253d83cafa80
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/RtlSubtreeSuccessor, rtlref_65e50284-427f-47d9-92c7-719b8bc1bab5.xml, RtlSubtreeSuccessor, ifsk.rtlsubtreesuccessor, RtlSubtreeSuccessor routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlSubtreeSuccessor
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# RtlSubtreeSuccessor function


## -description


The <b>RtlSubtreeSuccessor</b> routine returns a pointer to the successor of the specified node within the subtree that is rooted at that node. 


## -syntax


````
PRTL_SPLAY_LINKS RtlSubtreeSuccessor(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters




### -param Links [in]

A pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>. 


## -returns



<b>RtlSubtreeSuccessor</b> returns a pointer to the subtree successor of the node at <i>Links</i>, or <b>NULL</b> if the given node has no subtree successor. 




## -remarks



If the node at <i>Links</i> has a right subtree, the leftmost node of that subtree is the subtree successor. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlSubtreeSuccessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. If the tree is paged, callers must be running at IRQL &lt; DISPATCH_LEVEL. Usually callers are running at IRQL PASSIVE_LEVEL. 




## -see-also

<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>



<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>



<a href="..\ntddk\nf-ntddk-rtlsubtreepredecessor.md">RtlSubtreePredecessor</a>



<a href="..\ntddk\nf-ntddk-rtlsubtreepredecessor.md">RtlSubtreePredecessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSubtreeSuccessor routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

