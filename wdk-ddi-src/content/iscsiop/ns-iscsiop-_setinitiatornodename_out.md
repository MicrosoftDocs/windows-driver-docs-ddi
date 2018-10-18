---
UID: NS:iscsiop._SetInitiatorNodeName_OUT
title: "_SetInitiatorNodeName_OUT"
author: windows-driver-content
description: The SetInitiatorNodeName_OUT structure holds the output data for the SetInitiatorNodeName method.
old-location: storage\setinitiatornodename_out.htm
tech.root: storage
ms.assetid: f3417648-f9f9-402f-b3a3-d09c0b7e5fdd
ms.date: 3/29/2018
ms.keywords: "*PSetInitiatorNodeName_OUT, PSetInitiatorNodeName_OUT, PSetInitiatorNodeName_OUT structure pointer [Storage Devices], SetInitiatorNodeName_OUT, SetInitiatorNodeName_OUT structure [Storage Devices], _SetInitiatorNodeName_OUT, iscsiop/PSetInitiatorNodeName_OUT, iscsiop/SetInitiatorNodeName_OUT, storage.setinitiatornodename_out, structs-iSCSI_35ce4900-1703-4562-abe0-155215893c5f.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	SetInitiatorNodeName_OUT
product:
- Windows
targetos: Windows
req.typenames: SetInitiatorNodeName_OUT, *PSetInitiatorNodeName_OUT
---

# _SetInitiatorNodeName_OUT structure


## -description


The SetInitiatorNodeName_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565706">SetInitiatorNodeName</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>SetInitiatorNodeName</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565706">SetInitiatorNodeName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565729">SetInitiatorNodeName_IN</a>
 

 

