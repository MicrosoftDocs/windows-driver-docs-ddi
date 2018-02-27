---
UID: NF:wdm.ClfsLsnBlockOffset
title: ClfsLsnBlockOffset function
author: windows-driver-content
description: The ClfsLsnBlockOffset routine returns the sector-aligned block offset contained in a specified LSN.
old-location: kernel\clfslsnblockoffset.htm
old-project: kernel
ms.assetid: 8b2cf728-8859-4b7d-99f0-2ee7604ab480
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ClfsLsnBlockOffset, ClfsLsnBlockOffset routine [Kernel-Mode Driver Architecture], Clfs_700ff9e8-40ea-4659-b4a5-99432fb1577c.xml, kernel.clfslsnblockoffset, wdm/ClfsLsnBlockOffset
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
-	ClfsLsnBlockOffset
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsLsnBlockOffset function


## -description


The <b>ClfsLsnBlockOffset</b> routine returns the sector-aligned block offset contained in a specified LSN.


## -syntax


````
ULONG ClfsLsnBlockOffset(
  _In_ const CLFS_LSN *plsn
);
````


## -parameters




### -param plsn [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure from which the block offset is retrieved.


## -returns



<b>ClfsLsnBlockOffset</b> returns the block offset contained in the LSN that is supplied by the caller.




## -remarks



The block offset returned by this routine is a multiple of the sector size on the stable storage medium. For example, if the sector size is 1024 bytes, the block offset is a multiple of 1024. 

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="..\wdm\nf-wdm-clfslsnrecordsequence.md">ClfsLsnRecordSequence</a>



<a href="..\wdm\nf-wdm-clfslsncontainer.md">ClfsLsnContainer</a>



<a href="..\wdm\nf-wdm-clfslsncreate.md">ClfsLsnCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnBlockOffset routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

