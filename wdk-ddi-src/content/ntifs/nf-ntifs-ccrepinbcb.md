---
UID: NF:ntifs.CcRepinBcb
title: CcRepinBcb function
author: windows-driver-content
description: The CcRepinBcb routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to CcUnpinData.
old-location: ifsk\ccrepinbcb.htm
old-project: ifsk
ms.assetid: 81c2446e-8f11-4146-8da5-17fc451c2729
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcRepinBcb, CcRepinBcb routine [Installable File System Drivers], ccref_5aacfd67-3d6c-4be6-9bfa-5b85772ce32f.xml, ifsk.ccrepinbcb, ntifs/CcRepinBcb
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcRepinBcb
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcRepinBcb function


## -description


The <b>CcRepinBcb</b> routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>.


## -parameters




### -param Bcb [in]

Buffer control block (BCB) pointer returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>.


## -returns



None




## -remarks



File systems call <b>CcRepinBcb</b> to preserve a BCB for write-through or error recovery. Typically a file system would do this the first time it marks a BCB as dirty while processing a write-through request, or any time that it determines that a buffer will be required for write-through.

Every call to <b>CcRepinBcb</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539235">CcUnpinRepinnedBcb</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539180">CcPinRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539183">CcPreparePinWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539235">CcUnpinRepinnedBcb</a>
 

 

