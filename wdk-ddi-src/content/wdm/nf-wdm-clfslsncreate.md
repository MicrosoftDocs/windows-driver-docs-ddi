---
UID: NF:wdm.ClfsLsnCreate
title: ClfsLsnCreate function (wdm.h)
description: The ClfsLsnCreate routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.
old-location: kernel\clfslsncreate.htm
tech.root: kernel
ms.assetid: 2b183911-0c4d-4b67-834d-e876d22c99af
ms.date: 04/30/2018
keywords: ["ClfsLsnCreate function"]
ms.keywords: ClfsLsnCreate, ClfsLsnCreate routine [Kernel-Mode Driver Architecture], Clfs_5eea5630-3db0-45bb-8e16-c9e69081f972.xml, kernel.clfslsncreate, wdm/ClfsLsnCreate
f1_keywords:
 - "wdm/ClfsLsnCreate"
 - "ClfsLsnCreate"
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
- ClfsLsnCreate
targetos: Windows
req.typenames: 
---

# ClfsLsnCreate function


## -description


The <b>ClfsLsnCreate</b> routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.


## -parameters




### -param cidContainer 
[in]
An integer in the range 0x0 through 0xFFFFFFFF that supplies the container identifier.


### -param offBlock 
[in]
The block offset. This parameter must be a multiple of 512.


### -param cRecord 
[in]
An integer in the range 0 - 511 that supplies the record sequence number.


## -returns



<b>ClfsLsnCreate</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that represents the container identifier, block offset, and record sequence number supplied by the caller.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

systems.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnblockoffset">ClfsLsnBlockOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsncontainer">ClfsLsnContainer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnrecordsequence">ClfsLsnRecordSequence</a>
 

 

