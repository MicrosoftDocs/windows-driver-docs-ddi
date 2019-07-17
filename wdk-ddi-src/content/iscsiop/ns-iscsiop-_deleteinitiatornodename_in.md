---
UID: NS:iscsiop._DeleteInitiatorNodeName_IN
title: _DeleteInitiatorNodeName_IN (iscsiop.h)
description: The DeleteInitiatorNodeName_IN structure holds the input data for the DeleteInitiatorNodeName method, which is used to delete an initiator node name.
old-location: storage\deleteinitiatornodename_in.htm
tech.root: storage
ms.assetid: 10b6660c-7f48-4717-89d4-d6a5eb6594c8
ms.date: 03/29/2018
ms.keywords: "*PDeleteInitiatorNodeName_IN, DeleteInitiatorNodeName_IN, DeleteInitiatorNodeName_IN structure [Storage Devices], PDeleteInitiatorNodeName_IN, PDeleteInitiatorNodeName_IN structure pointer [Storage Devices], _DeleteInitiatorNodeName_IN, iscsiop/DeleteInitiatorNodeName_IN, iscsiop/PDeleteInitiatorNodeName_IN, storage.deleteinitiatornodename_in, structs-iSCSI_2b687a5a-17af-4eda-b48f-8e7ca06024f2.xml"
ms.topic: struct
f1_keywords:
 - "iscsiop/DeleteInitiatorNodeName_IN"
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
- DeleteInitiatorNodeName_IN
product:
- Windows
targetos: Windows
req.typenames: DeleteInitiatorNodeName_IN, *PDeleteInitiatorNodeName_IN
---

# _DeleteInitiatorNodeName_IN structure


## -description


The DeleteInitiatorNodeName_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/deleteinitiatornodename">DeleteInitiatorNodeName</a> method, which is used to delete an initiator node name.


## -struct-fields




### -field DeletedInitiatorName

The iSCSI initiator node name that is to be deleted.


## -remarks



It is optional that you implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/deleteinitiatornodename">DeleteInitiatorNodeName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsiop/ns-iscsiop-_deleteinitiatornodename_out">DeleteInitiatorNodeName_OUT</a>
 

 

