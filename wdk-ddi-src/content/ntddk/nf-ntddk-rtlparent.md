---
UID: NF:ntddk.RtlParent
title: RtlParent macro
author: windows-driver-content
description: The RtlParent routine returns a pointer to the parent of the specified node in a splay link tree.
old-location: ifsk\rtlparent.htm
old-project: ifsk
ms.assetid: 940c9234-6c4e-421d-a3e3-87ba2d786248
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: rtlref_85e6ffbf-9d34-47f5-b5c2-1d57a1a57056.xml, ntddk/RtlParent, ifsk.rtlparent, RtlParent routine [Installable File System Drivers], RtlParent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: ntddk.h
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	RtlParent
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# RtlParent macro


## -description


The <b>RtlParent</b> routine returns a pointer to the parent of the specified node in a splay link tree. 


## -syntax


````
PRTL_SPLAY_LINKS RtlParent(
  _In_ PRTL_SPLAY_LINKS Links
);
````


## -parameters




### -param Links [in]

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## -remarks



<b>RtlParent</b> can be called repeatedly in conjunction with <b>RtlLeftChild</b> and <b>RtlRightChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlParent</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL. 




## -see-also

<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>



<a href="..\ntddk\nf-ntddk-rtlisroot.md">RtlIsRoot</a>



<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>



<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>



<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>



<a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlParent routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

