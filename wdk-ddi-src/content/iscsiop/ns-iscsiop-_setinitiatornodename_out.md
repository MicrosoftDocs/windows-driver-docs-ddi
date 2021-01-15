---
UID: NS:iscsiop._SetInitiatorNodeName_OUT
title: _SetInitiatorNodeName_OUT (iscsiop.h)
description: The SetInitiatorNodeName_OUT structure holds the output data for the SetInitiatorNodeName method.
old-location: storage\setinitiatornodename_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SetInitiatorNodeName_OUT structure"]
ms.keywords: "*PSetInitiatorNodeName_OUT, PSetInitiatorNodeName_OUT, PSetInitiatorNodeName_OUT structure pointer [Storage Devices], SetInitiatorNodeName_OUT, SetInitiatorNodeName_OUT structure [Storage Devices], _SetInitiatorNodeName_OUT, iscsiop/PSetInitiatorNodeName_OUT, iscsiop/SetInitiatorNodeName_OUT, storage.setinitiatornodename_out, structs-iSCSI_35ce4900-1703-4562-abe0-155215893c5f.xml"
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
req.typenames: SetInitiatorNodeName_OUT, *PSetInitiatorNodeName_OUT
f1_keywords:
 - _SetInitiatorNodeName_OUT
 - iscsiop/_SetInitiatorNodeName_OUT
 - PSetInitiatorNodeName_OUT
 - iscsiop/PSetInitiatorNodeName_OUT
 - SetInitiatorNodeName_OUT
 - iscsiop/SetInitiatorNodeName_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - _SetInitiatorNodeName_OUT
 - PSetInitiatorNodeName_OUT
 - SetInitiatorNodeName_OUT
---

# _SetInitiatorNodeName_OUT structure


## -description

The SetInitiatorNodeName_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/setinitiatornodename">SetInitiatorNodeName</a> method.

## -struct-fields

### -field Status

On output, the status of the <b>SetInitiatorNodeName</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

It is optional that you implement this class.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/setinitiatornodename">SetInitiatorNodeName</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setinitiatornodename_in">SetInitiatorNodeName_IN</a>

