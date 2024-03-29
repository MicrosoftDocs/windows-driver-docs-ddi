---
UID: NF:wdm.ClfsLsnGreater
title: ClfsLsnGreater function (wdm.h)
description: The ClfsLsnGreater routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream.
old-location: kernel\clfslsngreater.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ClfsLsnGreater function"]
ms.keywords: ClfsLsnGreater, ClfsLsnGreater routine [Kernel-Mode Driver Architecture], Clfs_e258803f-9e95-4601-9b4e-2d775836864b.xml, kernel.clfslsngreater, wdm/ClfsLsnGreater
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsLsnGreater
 - wdm/ClfsLsnGreater
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsLsnGreater
---

# ClfsLsnGreater function


## -description

The <b>ClfsLsnGreater</b> routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream.

## -parameters

### -param plsn1 [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.

### -param plsn2 [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies the other LSN to be compared.

## -returns

<b>ClfsLsnGreater</b> returns <b>TRUE</b> if <i>plsn1</i> is strictly greater than <i>plsn2</i>; otherwise, it returns <b>FALSE</b>.

## -remarks

CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnGreater</b>.

LSNs from different streams are not comparable. Do not use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnequal">ClfsLsnEqual</a>, <b>ClfsLsnGreater</b>, and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnequal">ClfsLsnEqual</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnless">ClfsLsnLess</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnnull">ClfsLsnNull</a>
