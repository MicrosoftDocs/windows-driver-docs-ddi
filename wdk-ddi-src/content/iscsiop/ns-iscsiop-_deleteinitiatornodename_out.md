---
UID: NS:iscsiop._DeleteInitiatorNodeName_OUT
title: _DeleteInitiatorNodeName_OUT (iscsiop.h)
description: The DeleteInitiatorNodeName_OUT structure holds the output data for the DeleteInitiatorNodeName method.
old-location: storage\deleteinitiatornodename_out.htm
tech.root: storage
ms.assetid: 105f6687-ea0f-45e9-be44-eafdd06156eb
ms.date: 03/29/2018
keywords: ["DeleteInitiatorNodeName_OUT structure"]
ms.keywords: "*PDeleteInitiatorNodeName_OUT, DeleteInitiatorNodeName_OUT, DeleteInitiatorNodeName_OUT structure [Storage Devices], PDeleteInitiatorNodeName_OUT, PDeleteInitiatorNodeName_OUT structure pointer [Storage Devices], _DeleteInitiatorNodeName_OUT, iscsiop/DeleteInitiatorNodeName_OUT, iscsiop/PDeleteInitiatorNodeName_OUT, storage.deleteinitiatornodename_out, structs-iSCSI_2a85602a-f8f8-45c5-948d-128e3f5621a0.xml"
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
targetos: Windows
req.typenames: DeleteInitiatorNodeName_OUT, *PDeleteInitiatorNodeName_OUT
f1_keywords:
 - _DeleteInitiatorNodeName_OUT
 - iscsiop/_DeleteInitiatorNodeName_OUT
 - PDeleteInitiatorNodeName_OUT
 - iscsiop/PDeleteInitiatorNodeName_OUT
 - DeleteInitiatorNodeName_OUT
 - iscsiop/DeleteInitiatorNodeName_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - DeleteInitiatorNodeName_OUT
---

# _DeleteInitiatorNodeName_OUT structure


## -description

The DeleteInitiatorNodeName_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/deleteinitiatornodename">DeleteInitiatorNodeName</a> method.

## -struct-fields

### -field Status

The status of the <b>DeleteInitiatorNodeName</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

It is optional that you implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/deleteinitiatornodename">DeleteInitiatorNodeName</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_deleteinitiatornodename_in">DeleteInitiatorNodeName_IN</a>



<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>