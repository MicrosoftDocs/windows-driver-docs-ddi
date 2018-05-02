---
UID: NF:wdm.ClfsLsnRecordSequence
title: ClfsLsnRecordSequence function
author: windows-driver-content
description: The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN.
old-location: kernel\clfslsnrecordsequence.htm
old-project: kernel
ms.assetid: 407675de-4a06-49f7-9b43-c48b4c84ac7e
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ClfsLsnRecordSequence, ClfsLsnRecordSequence routine [Kernel-Mode Driver Architecture], Clfs_a78f7923-d295-408c-9a52-16e5cc38ca31.xml, kernel.clfslsnrecordsequence, wdm/ClfsLsnRecordSequence
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
-	ClfsLsnRecordSequence
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsLsnRecordSequence function


## -description


The <b>ClfsLsnRecordSequence</b> routine returns the record sequence number contained in a specified LSN.


## -parameters




### -param plsn [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure from which the record sequence number is retrieved.


## -returns



<b>ClfsLsnRecordSequence</b> returns the record sequence number contained in the LSN that is supplied by the caller.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541569">ClfsLsnBlockOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541573">ClfsLsnContainer</a>
 

 

