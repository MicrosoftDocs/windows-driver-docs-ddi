---
UID: NS:iscsiop._SendTargets_IN
title: _SendTargets_IN (iscsiop.h)
description: The SendTargets_IN structure holds the input data for the SendTargets method.
old-location: storage\sendtargets_in.htm
tech.root: storage
ms.assetid: fa6af43c-4fbd-43b5-9c3d-61254dfe894f
ms.date: 03/29/2018
ms.keywords: "*PSendTargets_IN, PSendTargets_IN, PSendTargets_IN structure pointer [Storage Devices], SendTargets_IN, SendTargets_IN structure [Storage Devices], _SendTargets_IN, iscsiop/PSendTargets_IN, iscsiop/SendTargets_IN, storage.sendtargets_in, structs-iSCSI_448fb50f-6420-43ca-be0e-b3dd110cd48b.xml"
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- SendTargets_IN
product:
- Windows
targetos: Windows
req.typenames: SendTargets_IN, *PSendTargets_IN
---

# _SendTargets_IN structure


## -description


The SendTargets_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565526">SendTargets</a> method.


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The LoginToTarget and AddConnectionToSession methods both return this value in their UniqueSessionId parameter.


### -field SendTargetsText

The authentication key text in the PDU.


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565526">SendTargets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565540">SendTargets_OUT</a>
 

 

