---
UID: NF:wdm.ClfsLsnBlockOffset
title: ClfsLsnBlockOffset function
author: windows-driver-content
description: The ClfsLsnBlockOffset routine returns the sector-aligned block offset contained in a specified LSN.
old-location: kernel\clfslsnblockoffset.htm
old-project: kernel
ms.assetid: 8b2cf728-8859-4b7d-99f0-2ee7604ab480
ms.author: windowsdriverdev
ms.date: 4/5/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsLsnBlockOffset
product: Windows
targetos: Windows
req.typenames: 
---

# ClfsLsnBlockOffset function


## -description


The <b>ClfsLsnBlockOffset</b> routine returns the sector-aligned block offset contained in a specified LSN.


## -parameters




### -param plsn [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure from which the block offset is retrieved.


## -returns



<b>ClfsLsnBlockOffset</b> returns the block offset contained in the LSN that is supplied by the caller.




## -remarks



The block offset returned by this routine is a multiple of the sector size on the stable storage medium. For example, if the sector size is 1024 bytes, the block offset is a multiple of 1024. 

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541573">ClfsLsnContainer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541585">ClfsLsnCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541615">ClfsLsnRecordSequence</a>
 

 

