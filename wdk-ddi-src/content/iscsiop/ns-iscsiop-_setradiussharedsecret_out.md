---
UID: NS:iscsiop._SetRADIUSSharedSecret_OUT
title: _SetRADIUSSharedSecret_OUT (iscsiop.h)
description: The SetRADIUSSharedSecret_OUT structure holds the output data for the SetRADIUSSharedSecret method.
old-location: storage\setradiussharedsecret_out.htm
tech.root: storage
ms.assetid: 55be7611-3249-4109-a142-c0115dfebb98
ms.date: 03/29/2018
keywords: ["SetRADIUSSharedSecret_OUT structure"]
ms.keywords: "*PSetRADIUSSharedSecret_OUT, PSetRADIUSSharedSecret_OUT, PSetRADIUSSharedSecret_OUT structure pointer [Storage Devices], SetRADIUSSharedSecret_OUT, SetRADIUSSharedSecret_OUT structure [Storage Devices], _SetRADIUSSharedSecret_OUT, iscsiop/PSetRADIUSSharedSecret_OUT, iscsiop/SetRADIUSSharedSecret_OUT, storage.setradiussharedsecret_out, structs-iSCSI_497fc66e-8a5d-4390-9229-622b359776bc.xml"
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
req.typenames: SetRADIUSSharedSecret_OUT, *PSetRADIUSSharedSecret_OUT
f1_keywords:
 - _SetRADIUSSharedSecret_OUT
 - iscsiop/_SetRADIUSSharedSecret_OUT
 - PSetRADIUSSharedSecret_OUT
 - iscsiop/PSetRADIUSSharedSecret_OUT
 - SetRADIUSSharedSecret_OUT
 - iscsiop/SetRADIUSSharedSecret_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SetRADIUSSharedSecret_OUT
---

# _SetRADIUSSharedSecret_OUT structure


## -description

The SetRADIUSSharedSecret_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/setradiussharedsecret">SetRADIUSSharedSecret</a> method.

## -struct-fields

### -field Status

On output, the status of the <b>SetRADIUSSharedSecret</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/setradiussharedsecret">SetRADIUSSharedSecret</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setradiussharedsecret_in">SetRADIUSSharedSecret_IN</a>