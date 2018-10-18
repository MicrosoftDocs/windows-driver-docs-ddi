---
UID: NF:wdm.ClfsLsnEqual
title: ClfsLsnEqual function
author: windows-driver-content
description: The ClfsLsnEqual routine determines whether two LSNs from the same stream are equal.
old-location: kernel\clfslsnequal.htm
tech.root: kernel
ms.assetid: e154c9d5-a131-47db-b0fa-d51154637c56
ms.date: 4/30/2018
ms.keywords: ClfsLsnEqual, ClfsLsnEqual routine [Kernel-Mode Driver Architecture], Clfs_09dba2f1-3508-488d-b663-8ba0806b9d31.xml, kernel.clfslsnequal, wdm/ClfsLsnEqual
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
-	ClfsLsnEqual
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsLsnEqual function


## -description


The <b>ClfsLsnEqual</b> routine determines whether two LSNs from the same stream are equal.


## -parameters




### -param plsn1 [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.


### -param plsn2 [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that supplies the other LSN to be compared.


## -returns



<b>ClfsLsnEqual</b> returns <b>TRUE</b> if the two LSNs are equal; otherwise, it returns <b>FALSE</b>.




## -remarks



CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnEqual</b>.

LSNs from different streams are not comparable. Do not use <b>ClfsLsnEqual</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541595">ClfsLsnGreater</a>, and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541595">ClfsLsnGreater</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541608">ClfsLsnLess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541609">ClfsLsnNull</a>
 

 

