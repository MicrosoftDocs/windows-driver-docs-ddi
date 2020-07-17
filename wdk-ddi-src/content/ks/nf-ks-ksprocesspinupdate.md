---
UID: NF:ks.KsProcessPinUpdate
title: KsProcessPinUpdate function (ks.h)
description: The KsProcessPinUpdate function is called from within a filter-centric filter's AVStrMiniFilterProcess dispatch to update a process pin.
old-location: stream\ksprocesspinupdate.htm
tech.root: stream
ms.assetid: 9f6c28ad-d3dd-4be4-a637-10958a9cbd20
ms.date: 04/23/2018
keywords: ["KsProcessPinUpdate function"]
ms.keywords: KsProcessPinUpdate, KsProcessPinUpdate function [Streaming Media Devices], avfunc_8f096e7d-7eb1-40c7-bcc9-762e671bb3d4.xml, ks/KsProcessPinUpdate, stream.ksprocesspinupdate
f1_keywords:
 - "ks/KsProcessPinUpdate"
 - "KsProcessPinUpdate"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsProcessPinUpdate
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsProcessPinUpdate function


## -description


The <b>KsProcessPinUpdate</b> function is called from within a filter-centric filter's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfilterprocess">AVStrMiniFilterProcess</a> dispatch to update a process pin.


## -parameters




### -param ProcessPin [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a> structure that represents the process pin to update.


## -returns



<b>KsProcessPinUpdate</b> returns <b>TRUE</b> if <i>ProcessPin</i>'s conditions for processing are met; otherwise, it returns <b>FALSE</b>. (These conditions are set in the pin descriptor within the <b>Pin</b> member of <i>ProcessPin</i>.) If the minidriver's dispatch calls this routine while the filter is in the STOP state, <b>KsProcessPinUpdate</b> returns <b>FALSE</b> since no pipe exists.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a>
 

 

