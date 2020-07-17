---
UID: NF:wdm.ClfsLsnLess
title: ClfsLsnLess function (wdm.h)
description: The ClfsLsnLess routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream.
old-location: kernel\clfslsnless.htm
tech.root: kernel
ms.assetid: fbdf6e86-35a1-48a8-966a-0e5472466da2
ms.date: 04/30/2018
keywords: ["ClfsLsnLess function"]
ms.keywords: ClfsLsnLess, ClfsLsnLess routine [Kernel-Mode Driver Architecture], Clfs_5e0196f1-8244-4cf9-aa36-7359e52ff43b.xml, kernel.clfslsnless, wdm/ClfsLsnLess
f1_keywords:
 - "wdm/ClfsLsnLess"
 - "ClfsLsnLess"
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
- ClfsLsnLess
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsLsnLess function


## -description


The <b>ClfsLsnLess</b> routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream. 


## -parameters




### -param plsn1 [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.


### -param plsn2 [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies the other LSN to be compared.


## -returns



<b>ClfsLsnLess</b> returns <b>TRUE</b> if <i>plsn1</i> is strictly less than <i>plsn2</i>; otherwise, it returns <b>FALSE</b>.




## -remarks



CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnLess</b>. 

LSNs from different streams are not comparable. Do not use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnequal">ClfsLsnEqual</a>, <b>ClfsLsnLess</b> and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnequal">ClfsLsnEqual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsngreater">ClfsLsnGreater</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnnull">ClfsLsnNull</a>
 

 

