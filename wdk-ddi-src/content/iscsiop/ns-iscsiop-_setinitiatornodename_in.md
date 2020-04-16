---
UID: NS:iscsiop._SetInitiatorNodeName_IN
title: _SetInitiatorNodeName_IN (iscsiop.h)
description: The SetInitiatorNodeName_IN structure holds the input data for the SetInitiatorNodeName method.
old-location: storage\setinitiatornodename_in.htm
tech.root: storage
ms.assetid: 58af1872-23bf-44f2-9ef4-271f0ddef5d5
ms.date: 03/29/2018
keywords: ["_SetInitiatorNodeName_IN structure"]
ms.keywords: "*PSetInitiatorNodeName_IN, PSetInitiatorNodeName_IN, PSetInitiatorNodeName_IN structure pointer [Storage Devices], SetInitiatorNodeName_IN, SetInitiatorNodeName_IN structure [Storage Devices], _SetInitiatorNodeName_IN, iscsiop/PSetInitiatorNodeName_IN, iscsiop/SetInitiatorNodeName_IN, storage.setinitiatornodename_in, structs-iSCSI_fac4e524-8266-4135-9211-564d1ea2a952.xml"
f1_keywords:
 - "iscsiop/SetInitiatorNodeName_IN"
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
- SetInitiatorNodeName_IN
product:
- Windows
targetos: Windows
req.typenames: SetInitiatorNodeName_IN, *PSetInitiatorNodeName_IN
---

# _SetInitiatorNodeName_IN structure


## -description


The SetInitiatorNodeName_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setinitiatornodename">SetInitiatorNodeName</a> method.


## -struct-fields




### -field CreatedInitiatorName

The new initiator name.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setinitiatornodename">SetInitiatorNodeName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setinitiatornodename_out">SetInitiatorNodeName_OUT</a>
 

 

