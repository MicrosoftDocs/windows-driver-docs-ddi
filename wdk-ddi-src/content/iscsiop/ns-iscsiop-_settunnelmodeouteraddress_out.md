---
UID: NS:iscsiop._SetTunnelModeOuterAddress_OUT
title: _SetTunnelModeOuterAddress_OUT (iscsiop.h)
description: The SetTunnelModeOuterAddress_OUT structure holds the output data for the SetTunnelModeOuterAddress method.
old-location: storage\settunnelmodeouteraddress_out.htm
tech.root: storage
ms.assetid: 2cfe935f-eba4-48aa-869d-6381ca038e70
ms.date: 03/29/2018
keywords: ["SetTunnelModeOuterAddress_OUT structure"]
ms.keywords: "*PSetTunnelModeOuterAddress_OUT, PSetTunnelModeOuterAddress_OUT, PSetTunnelModeOuterAddress_OUT structure pointer [Storage Devices], SetTunnelModeOuterAddress_OUT, SetTunnelModeOuterAddress_OUT structure [Storage Devices], _SetTunnelModeOuterAddress_OUT, iscsiop/PSetTunnelModeOuterAddress_OUT, iscsiop/SetTunnelModeOuterAddress_OUT, storage.settunnelmodeouteraddress_out, structs-iSCSI_918f9bb3-ee9f-41d3-8e9e-c18a673a4302.xml"
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
req.typenames: SetTunnelModeOuterAddress_OUT, *PSetTunnelModeOuterAddress_OUT
f1_keywords:
 - _SetTunnelModeOuterAddress_OUT
 - iscsiop/_SetTunnelModeOuterAddress_OUT
 - PSetTunnelModeOuterAddress_OUT
 - iscsiop/PSetTunnelModeOuterAddress_OUT
 - SetTunnelModeOuterAddress_OUT
 - iscsiop/SetTunnelModeOuterAddress_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SetTunnelModeOuterAddress_OUT
---

# _SetTunnelModeOuterAddress_OUT structure


## -description

The SetTunnelModeOuterAddress_OUT structure holds the output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/settunnelmodeouteraddress">SetTunnelModeOuterAddress</a> method.

## -struct-fields

### -field Status

On output, the status of the <b>SetTunnelModeOuterAddress</b> operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

You must implement this method.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/settunnelmodeouteraddress">SetTunnelModeOuterAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_settunnelmodeouteraddress_in">SetTunnelModeOuterAddress_IN</a>

