---
UID: NF:ntifs.CcRepinBcb
title: CcRepinBcb function
author: windows-driver-content
description: The CcRepinBcb routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to CcUnpinData.
old-location: ifsk\ccrepinbcb.htm
old-project: ifsk
ms.assetid: 81c2446e-8f11-4146-8da5-17fc451c2729
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcRepinBcb routine [Installable File System Drivers], ntifs/CcRepinBcb, CcRepinBcb, ifsk.ccrepinbcb, ccref_5aacfd67-3d6c-4be6-9bfa-5b85772ce32f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcRepinBcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcRepinBcb function


## -description


The <b>CcRepinBcb</b> routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>.


## -syntax


````
VOID CcRepinBcb(
  _In_ PVOID Bcb
);
````


## -parameters




### -param Bcb [in]

Buffer control block (BCB) pointer returned by <a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a> or <a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>.


## -returns


None



## -remarks


File systems call <b>CcRepinBcb</b> to preserve a BCB for write-through or error recovery. Typically a file system would do this the first time it marks a BCB as dirty while processing a write-through request, or any time that it determines that a buffer will be required for write-through.

Every call to <b>CcRepinBcb</b> must be matched by a subsequent call to <a href="..\ntifs\nf-ntifs-ccunpinrepinnedbcb.md">CcUnpinRepinnedBcb</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>

<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>

<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>

<a href="..\ntifs\nf-ntifs-ccunpinrepinnedbcb.md">CcUnpinRepinnedBcb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcRepinBcb routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

