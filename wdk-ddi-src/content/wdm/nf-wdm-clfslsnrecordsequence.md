---
UID: NF:wdm.ClfsLsnRecordSequence
title: ClfsLsnRecordSequence function (wdm.h)
description: The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN.
old-location: kernel\clfslsnrecordsequence.htm
tech.root: kernel
ms.assetid: 407675de-4a06-49f7-9b43-c48b4c84ac7e
ms.date: 04/30/2018
ms.keywords: ClfsLsnRecordSequence, ClfsLsnRecordSequence routine [Kernel-Mode Driver Architecture], Clfs_a78f7923-d295-408c-9a52-16e5cc38ca31.xml, kernel.clfslsnrecordsequence, wdm/ClfsLsnRecordSequence
f1_keywords:
 - "wdm/ClfsLsnRecordSequence"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsLsnRecordSequence
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

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure from which the record sequence number is retrieved.


## -returns



<b>ClfsLsnRecordSequence</b> returns the record sequence number contained in the LSN that is supplied by the caller.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnblockoffset">ClfsLsnBlockOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsncontainer">ClfsLsnContainer</a>
 

 

