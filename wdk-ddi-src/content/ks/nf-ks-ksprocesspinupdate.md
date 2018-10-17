---
UID: NF:ks.KsProcessPinUpdate
title: KsProcessPinUpdate function
author: windows-driver-content
description: The KsProcessPinUpdate function is called from within a filter-centric filter's AVStrMiniFilterProcess dispatch to update a process pin.
old-location: stream\ksprocesspinupdate.htm
tech.root: stream
ms.assetid: 9f6c28ad-d3dd-4be4-a637-10958a9cbd20
ms.date: 4/23/2018
ms.keywords: KsProcessPinUpdate, KsProcessPinUpdate function [Streaming Media Devices], avfunc_8f096e7d-7eb1-40c7-bcc9-762e671bb3d4.xml, ks/KsProcessPinUpdate, stream.ksprocesspinupdate
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsProcessPinUpdate
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsProcessPinUpdate function


## -description


The <b>KsProcessPinUpdate</b> function is called from within a filter-centric filter's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556315">AVStrMiniFilterProcess</a> dispatch to update a process pin.


## -parameters




### -param ProcessPin [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564256">KSPROCESSPIN</a> structure that represents the process pin to update.


## -returns



<b>KsProcessPinUpdate</b> returns <b>TRUE</b> if <i>ProcessPin</i>'s conditions for processing are met; otherwise, it returns <b>FALSE</b>. (These conditions are set in the pin descriptor within the <b>Pin</b> member of <i>ProcessPin</i>.) If the minidriver's dispatch calls this routine while the filter is in the STOP state, <b>KsProcessPinUpdate</b> returns <b>FALSE</b> since no pipe exists.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564256">KSPROCESSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564260">KSPROCESSPIN_INDEXENTRY</a>
 

 

