---
UID: NS:iscsiop._GetPresharedKeyForId_OUT
title: _GetPresharedKeyForId_OUT (iscsiop.h)
description: The GetPresharedKeyForId_OUT structure holds the output data for the GetPresharedKeyForId method.
old-location: storage\getpresharedkeyforid_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["GetPresharedKeyForId_OUT structure"]
ms.keywords: "*PGetPresharedKeyForId_OUT, GetPresharedKeyForId_OUT, GetPresharedKeyForId_OUT structure [Storage Devices], PGetPresharedKeyForId_OUT, PGetPresharedKeyForId_OUT structure pointer [Storage Devices], _GetPresharedKeyForId_OUT, iscsiop/GetPresharedKeyForId_OUT, iscsiop/PGetPresharedKeyForId_OUT, storage.getpresharedkeyforid_out, structs-iSCSI_6807c82b-45b4-44c7-a1e0-a99607c1cd4f.xml"
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
req.typenames: GetPresharedKeyForId_OUT, *PGetPresharedKeyForId_OUT
f1_keywords:
 - _GetPresharedKeyForId_OUT
 - iscsiop/_GetPresharedKeyForId_OUT
 - PGetPresharedKeyForId_OUT
 - iscsiop/PGetPresharedKeyForId_OUT
 - GetPresharedKeyForId_OUT
 - iscsiop/GetPresharedKeyForId_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - GetPresharedKeyForId_OUT
---

# _GetPresharedKeyForId_OUT structure


## -description

The GetPresharedKeyForId_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/getpresharedkeyforid">GetPresharedKeyForId</a> method.

## -struct-fields

### -field Status

On output from <b>GetPresharedKeyForId</b>, the status of the <b>GetPresharedKeyForId</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

### -field SecurityFlags

A bitwise OR of flags that indicate the security requirements of a target.  For a list of possible values for this member, see <a href="/windows-hardware/drivers/storage/security-flag-qualifiers">SECURITY_FLAG_QUALIFIERS</a>.

## -remarks

You must initiate this method if the initiator supports IKE.

## -see-also

<a href="/windows-hardware/drivers/storage/getpresharedkeyforid">GetPresharedKeyForId</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_getpresharedkeyforid_in">GetPresharedKeyForId_IN</a>



<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/msiscsi-securityconfigoperations-wmi-class">MSiSCSI_SecurityConfigOperations WMI Class</a>



<a href="/windows-hardware/drivers/storage/security-flag-qualifiers">SECURITY_FLAG_QUALIFIERS</a>
