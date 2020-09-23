---
UID: NF:wdm.ClfsLsnEqual
title: ClfsLsnEqual function (wdm.h)
description: The ClfsLsnEqual routine determines whether two LSNs from the same stream are equal.
old-location: kernel\clfslsnequal.htm
tech.root: kernel
ms.assetid: e154c9d5-a131-47db-b0fa-d51154637c56
ms.date: 04/30/2018
keywords: ["ClfsLsnEqual function"]
ms.keywords: ClfsLsnEqual, ClfsLsnEqual routine [Kernel-Mode Driver Architecture], Clfs_09dba2f1-3508-488d-b663-8ba0806b9d31.xml, kernel.clfslsnequal, wdm/ClfsLsnEqual
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
 - ClfsLsnEqual
 - wdm/ClfsLsnEqual
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsLsnEqual
---

# ClfsLsnEqual function


## -description

The <b>ClfsLsnEqual</b> routine determines whether two LSNs from the same stream are equal.

## -parameters

### -param plsn1 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.

### -param plsn2 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies the other LSN to be compared.

## -returns

<b>ClfsLsnEqual</b> returns <b>TRUE</b> if the two LSNs are equal; otherwise, it returns <b>FALSE</b>.

## -remarks

CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnEqual</b>.

LSNs from different streams are not comparable. Do not use <b>ClfsLsnEqual</b>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsngreater">ClfsLsnGreater</a>, and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsngreater">ClfsLsnGreater</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnless">ClfsLsnLess</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfslsnnull">ClfsLsnNull</a>