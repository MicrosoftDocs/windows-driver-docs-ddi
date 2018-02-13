---
UID: NF:wdm.ClfsLsnLess
title: ClfsLsnLess function
author: windows-driver-content
description: The ClfsLsnLess routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream.
old-location: kernel\clfslsnless.htm
old-project: kernel
ms.assetid: fbdf6e86-35a1-48a8-966a-0e5472466da2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsLsnLess, kernel.clfslsnless, ClfsLsnLess routine [Kernel-Mode Driver Architecture], wdm/ClfsLsnLess, Clfs_5e0196f1-8244-4cf9-aa36-7359e52ff43b.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsLsnLess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsLsnLess function


## -description


The <b>ClfsLsnLess</b> routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream. 


## -syntax


````
BOOLEAN ClfsLsnLess(
  _In_ const CLFS_LSN *plsn1,
  _In_ const CLFS_LSN *plsn2
);
````


## -parameters




### -param plsn1 [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.


### -param plsn2 [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies the other LSN to be compared.


## -returns



<b>ClfsLsnLess</b> returns <b>TRUE</b> if <i>plsn1</i> is strictly less than <i>plsn2</i>; otherwise, it returns <b>FALSE</b>.




## -remarks



CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnLess</b>. 

LSNs from different streams are not comparable. Do not use <a href="..\wdm\nf-wdm-clfslsnequal.md">ClfsLsnEqual</a>, <b>ClfsLsnLess</b> and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.




## -see-also

<a href="..\wdm\nf-wdm-clfslsngreater.md">ClfsLsnGreater</a>



<a href="..\wdm\nf-wdm-clfslsnequal.md">ClfsLsnEqual</a>



<a href="..\wdm\nf-wdm-clfslsnnull.md">ClfsLsnNull</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnLess routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

