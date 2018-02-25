---
UID: NF:wdm.ClfsLsnContainer
title: ClfsLsnContainer function
author: windows-driver-content
description: The ClfsLsnContainer routine returns the logical container identifier contained in a specified LSN.
old-location: kernel\clfslsncontainer.htm
old-project: kernel
ms.assetid: 006edbf7-b3f8-45f2-902e-03d86e83b0a0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, ClfsLsnContainer, ClfsLsnContainer routine [Kernel-Mode Driver Architecture], Clfs_87c1e289-57b7-414d-a78e-8074a75d1262.xml, L, a, e, f, i, kernel.clfslsncontainer, l, n, o, r, s, t, wdm/ClfsLsnContainer"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsLsnContainer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsLsnContainer function


## -description


The <b>ClfsLsnContainer</b> routine returns the logical container identifier contained in a specified LSN.


## -syntax


````
CLFS_CONTAINER_ID ClfsLsnContainer(
  _In_ const CLFS_LSN *plsn
);
````


## -parameters




### -param plsn [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure from which the container identifier is retrieved.


## -returns



<b>ClfsLsnContainer</b> returns the logical container identifier contained in the LSN that is supplied by the caller. The logical container identifier is not necessarily the same as the identifier of the physical container on stable storage.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.




## -see-also

<a href="..\wdm\nf-wdm-clfslsnrecordsequence.md">ClfsLsnRecordSequence</a>



<a href="..\wdm\nf-wdm-clfslsncreate.md">ClfsLsnCreate</a>



<a href="..\wdm\nf-wdm-clfslsnblockoffset.md">ClfsLsnBlockOffset</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnContainer routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

