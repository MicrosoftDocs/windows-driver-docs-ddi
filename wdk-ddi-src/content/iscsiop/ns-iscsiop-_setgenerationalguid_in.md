---
UID: NS:iscsiop._SetGenerationalGuid_IN
title: _SetGenerationalGuid_IN (iscsiop.h)
description: The SetGenerationalGuid_IN structure holds the input data for the SetGenerationalGuid method.
old-location: storage\setgenerationalguid_in.htm
tech.root: storage
ms.assetid: 24568c37-9641-4e3e-b788-f71db4f3f70f
ms.date: 03/29/2018
ms.keywords: "*PSetGenerationalGuid_IN, PSetGenerationalGuid_IN, PSetGenerationalGuid_IN structure pointer [Storage Devices], SetGenerationalGuid_IN, SetGenerationalGuid_IN structure [Storage Devices], _SetGenerationalGuid_IN, iscsiop/PSetGenerationalGuid_IN, iscsiop/SetGenerationalGuid_IN, storage.setgenerationalguid_in, structs-iSCSI_e40eec29-19af-4f5a-8c5f-11b40c76ae0c.xml"
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
- SetGenerationalGuid_IN
product:
- Windows
targetos: Windows
req.typenames: SetGenerationalGuid_IN, *PSetGenerationalGuid_IN
---

# _SetGenerationalGuid_IN structure


## -description


The SetGenerationalGuid_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a> method.


## -struct-fields




### -field GenerationalGuid

A 16-byte GUID that identifies the version of the information that is currently in the initiator cache. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565687">SetGenerationalGuid_OUT</a>
 

 

