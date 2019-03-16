---
UID: NF:ks.KsFilterReleaseControl
title: KsFilterReleaseControl function (ks.h)
description: The KsFilterReleaseControl function releases the control mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilterreleasecontrol.htm
tech.root: stream
ms.assetid: 4f868e88-ef5c-4fad-be53-2b5116a6385b
ms.date: 04/23/2018
ms.keywords: KsFilterReleaseControl, KsFilterReleaseControl function [Streaming Media Devices], avfunc_ca99338c-1cae-4ef4-8ef5-76ee368ae1d6.xml, ks/KsFilterReleaseControl, stream.ksfilterreleasecontrol
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsFilterReleaseControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterReleaseControl function


## -description


The<b> KsFilterReleaseControl </b>function releases the control mutex for the AVStream filter specified by <i>Filter</i>.


## -parameters




### -param Filter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure representing the AVStream filter for which to release the control mutex.


## -returns



None




## -remarks



This function is an inline call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a> with the appropriate typecasting. When manipulating a filter, minidrivers should call this function instead of calling <b>KsReleaseControl</b> directly.

For a description of the filter control mutex, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562523">KsFilterAcquireControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566780">KsReleaseControl</a>
 

 

