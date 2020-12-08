---
UID: NS:iscsiop._AddRADIUSServer_OUT
title: _AddRADIUSServer_OUT (iscsiop.h)
description: The AddRADIUSServer_OUT structure holds the output data for the AddRADIUSServer method.
old-location: storage\addradiusserver_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AddRADIUSServer_OUT structure"]
ms.keywords: "*PAddRADIUSServer_OUT, AddRADIUSServer_OUT, AddRADIUSServer_OUT structure [Storage Devices], PAddRADIUSServer_OUT, PAddRADIUSServer_OUT structure pointer [Storage Devices], _AddRADIUSServer_OUT, iscsiop/AddRADIUSServer_OUT, iscsiop/PAddRADIUSServer_OUT, storage.addradiusserver_out, structs-iSCSI_4dd737cb-21a3-4f49-acbe-d40b5b172f3f.xml"
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
req.typenames: AddRADIUSServer_OUT, *PAddRADIUSServer_OUT
f1_keywords:
 - _AddRADIUSServer_OUT
 - iscsiop/_AddRADIUSServer_OUT
 - PAddRADIUSServer_OUT
 - iscsiop/PAddRADIUSServer_OUT
 - AddRADIUSServer_OUT
 - iscsiop/AddRADIUSServer_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - AddRADIUSServer_OUT
---

# _AddRADIUSServer_OUT structure


## -description

The AddRADIUSServer_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/addradiusserver">AddRADIUSServer</a> method.

## -struct-fields

### -field Status

On output from <b>AddRADIUSServer</b>, the status of the <b>AddRADIUSServer</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

It is optional that you implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/addradiusserver">AddRADIUSServer</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_addradiusserver_in">AddRADIUSServer_IN</a>



<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/msiscsi-operations-wmi-class">MSiSCSI_Operations WMI Class</a>
