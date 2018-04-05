---
UID: NF:wdm.ClfsLsnCreate
title: ClfsLsnCreate function
author: windows-driver-content
description: The ClfsLsnCreate routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.
old-location: kernel\clfslsncreate.htm
old-project: kernel
ms.assetid: 2b183911-0c4d-4b67-834d-e876d22c99af
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsLsnCreate, ClfsLsnCreate routine [Kernel-Mode Driver Architecture], Clfs_5eea5630-3db0-45bb-8e16-c9e69081f972.xml, kernel.clfslsncreate, wdm/ClfsLsnCreate
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
-	ClfsLsnCreate
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsLsnCreate function


## -description


The <b>ClfsLsnCreate</b> routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.


## -parameters




### -param cidContainer [in]

An integer in the range 0x0 through 0xFFFFFFFF that supplies the container identifier.


### -param offBlock [in]

The block offset. This parameter must be a multiple of 512.


### -param cRecord [in]

An integer in the range 0 - 511 that supplies the record sequence number.


## -returns



<b>ClfsLsnCreate</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that represents the container identifier, block offset, and record sequence number supplied by the caller.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

systems.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541569">ClfsLsnBlockOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541573">ClfsLsnContainer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541615">ClfsLsnRecordSequence</a>
 

 

