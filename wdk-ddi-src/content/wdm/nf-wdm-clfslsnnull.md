---
UID: NF:wdm.ClfsLsnNull
title: ClfsLsnNull function
author: windows-driver-content
description: The ClfsLsnNull routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL.
old-location: kernel\clfslsnnull.htm
tech.root: kernel
ms.assetid: 858fb84a-8df8-4748-ab09-3f7c4aca905c
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ClfsLsnNull, ClfsLsnNull routine [Kernel-Mode Driver Architecture], Clfs_26a9c0db-2336-4151-9de0-81a58ed9e2f0.xml, kernel.clfslsnnull, wdm/ClfsLsnNull
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
-	ClfsLsnNull
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsLsnNull function


## -description


The <b>ClfsLsnNull</b> routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL.


## -parameters




### -param plsn [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that supplies the LSN to be tested.


## -returns



<b>ClfsLsnNull</b> returns <b>TRUE</b> if the LSN supplied by the caller is equal to CLFS_LSN_NULL; otherwise, it returns <b>FALSE</b>.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541590">ClfsLsnEqual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541595">ClfsLsnGreater</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541608">ClfsLsnLess</a>
 

 

