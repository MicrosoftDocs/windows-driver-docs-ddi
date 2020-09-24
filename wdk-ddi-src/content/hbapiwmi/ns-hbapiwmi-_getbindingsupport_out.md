---
UID: NS:hbapiwmi._GetBindingSupport_OUT
title: _GetBindingSupport_OUT (hbapiwmi.h)
description: The GetBindingSupport_OUT structure is used by a WMI provider to report the output parameter data of the GetBindingSupport WMI method to the WMI client.
old-location: storage\getbindingsupport_out.htm
tech.root: storage
ms.assetid: cd67b301-a94a-41dd-9c06-e6c674ea9173
ms.date: 03/29/2018
keywords: ["GetBindingSupport_OUT structure"]
ms.keywords: "*PGetBindingSupport_OUT, GetBindingSupport_OUT, GetBindingSupport_OUT structure [Storage Devices], PGetBindingSupport_OUT, PGetBindingSupport_OUT structure pointer [Storage Devices], _GetBindingSupport_OUT, hbapiwmi/GetBindingSupport_OUT, hbapiwmi/PGetBindingSupport_OUT, storage.getbindingsupport_out, structs-Fibre_1db0b747-ead3-461f-a7ab-c8150f92623a.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.typenames: GetBindingSupport_OUT, *PGetBindingSupport_OUT
f1_keywords:
 - _GetBindingSupport_OUT
 - hbapiwmi/_GetBindingSupport_OUT
 - PGetBindingSupport_OUT
 - hbapiwmi/PGetBindingSupport_OUT
 - GetBindingSupport_OUT
 - hbapiwmi/GetBindingSupport_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - GetBindingSupport_OUT
---

# _GetBindingSupport_OUT structure


## -description

The GetBindingSupport_OUT structure is used by a WMI provider to report the output parameter data of the <a href="/windows-hardware/drivers/storage/getbindingsupport">GetBindingSupport</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field BindType

Contains a bitmap that indicates the ability of an HBA and its miniport driver to provide a specific set of features related to persistent binding. For a list of values that this parameter can have, see the description of the <a href="/windows-hardware/drivers/storage/hba-bind-type">HBA_BIND_TYPE</a> WMI class qualifier.

## -remarks

The WMI tool suite generates a declaration of the GetBindingSupport_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/getbindingsupport">GetBindingSupport</a>