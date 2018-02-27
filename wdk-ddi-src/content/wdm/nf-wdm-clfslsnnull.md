---
UID: NF:wdm.ClfsLsnNull
title: ClfsLsnNull function
author: windows-driver-content
description: The ClfsLsnNull routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL.
old-location: kernel\clfslsnnull.htm
old-project: kernel
ms.assetid: 858fb84a-8df8-4748-ab09-3f7c4aca905c
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsLsnNull function


## -description


The <b>ClfsLsnNull</b> routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL.


## -syntax


````
BOOLEAN ClfsLsnNull(
  _In_ const CLFS_LSN *plsn
);
````


## -parameters




### -param plsn [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies the LSN to be tested.


## -returns



<b>ClfsLsnNull</b> returns <b>TRUE</b> if the LSN supplied by the caller is equal to CLFS_LSN_NULL; otherwise, it returns <b>FALSE</b>.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="..\wdm\nf-wdm-clfslsngreater.md">ClfsLsnGreater</a>



<a href="..\wdm\nf-wdm-clfslsnless.md">ClfsLsnLess</a>



<a href="..\wdm\nf-wdm-clfslsnequal.md">ClfsLsnEqual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnNull routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

