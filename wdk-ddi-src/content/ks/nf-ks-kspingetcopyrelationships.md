---
UID: NF:ks.KsPinGetCopyRelationships
title: KsPinGetCopyRelationships function (ks.h)
description: The KsPinGetCopyRelationships function returns copy relationship information for a pin that is contained within a pin-centric filter.
old-location: stream\kspingetcopyrelationships.htm
tech.root: stream
ms.assetid: 7f74cbf1-2382-471c-ab07-fdb7e615cb0b
ms.date: 04/23/2018
ms.keywords: KsPinGetCopyRelationships, KsPinGetCopyRelationships function [Streaming Media Devices], avfunc_d44ce272-9171-4a32-89c6-023d9688fdfd.xml, ks/KsPinGetCopyRelationships, stream.kspingetcopyrelationships
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGetCopyRelationships
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetCopyRelationships function


## -description


The <b>KsPinGetCopyRelationships</b> function returns copy relationship information for a pin that is contained within a <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">pin-centric</a> filter.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure from which you want to acquire copy information.


### -param CopySource [out]

A pointer to a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure that is the copy source for <i>Pin</i>. If <i>Pin</i> is the copy source, AVStream sets this parameter to <b>NULL</b>.


### -param DelegateBranch [out]

A pointer to a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure that is the pin from which <i>Pin</i> receives delegated frames. If <i>Pin</i> is the delegator, AVStream sets this parameter to <b>NULL</b>.


## -returns



None




## -remarks




<a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-centric</a> filters receive similar <i>CopySource</i> and <i>DelegateBranch</i> information when AVStream calls the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556315">AVStrMiniFilterProcess</a> function with an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564260">KSPROCESSPIN_INDEXENTRY</a> structures.

The only difference is that <b>KsPinGetCopyRelationships</b> returns pointers to PKSPIN rather than pointers to PKSPROCESSPIN. For more information about the <i>CopySource</i> and <i>DelegateBranch</i> parameters, see <a href="https://msdn.microsoft.com/c2cfc183-0f4c-4104-a580-234e0483eee4">AVStream Splitters</a>.

All pins operate independently in the context of a pin-centric filter. As a result, a minidriver that calls <b>KsPinGetCopyRelationships</b> is responsible for ensuring that the appropriate synchronization is performed before call time.

To guarantee safety when calling <b>KsPinGetCopyRelationships</b>, either obtain the control mutex (do not use this mechanism in a processing dispatch) or make sure that the pin does not transition below <b>KSSTATE_PAUSE</b> while calling or using the information obtained. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

For more information, see <a href="https://msdn.microsoft.com/0b6a02c2-e672-4568-a890-491c721ec3a7">Pin-Centric Processing</a> and <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564256">KSPROCESSPIN</a>
 

 

