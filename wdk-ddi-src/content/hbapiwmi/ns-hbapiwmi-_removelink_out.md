---
UID: NS:hbapiwmi._RemoveLink_OUT
title: _RemoveLink_OUT (hbapiwmi.h)
description: The RemoveLink_OUT structure is used by an HBA miniport driver to report the output parameter data of the RemoveLink WMI method to the WMI client.
old-location: storage\removelink_out.htm
tech.root: storage
ms.assetid: 724e3143-4994-4785-9bbf-afb928e8b166
ms.date: 03/29/2018
keywords: ["RemoveLink_OUT structure"]
ms.keywords: "*PRemoveLink_OUT, PRemoveLink_OUT, PRemoveLink_OUT structure pointer [Storage Devices], RemoveLink_OUT, RemoveLink_OUT structure [Storage Devices], _RemoveLink_OUT, hbapiwmi/PRemoveLink_OUT, hbapiwmi/RemoveLink_OUT, storage.removelink_out, structs-Fibre_0210455d-c6c4-4548-ae14-63aa2e7b9a5d.xml"
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
req.typenames: RemoveLink_OUT, *PRemoveLink_OUT
f1_keywords:
 - _RemoveLink_OUT
 - hbapiwmi/_RemoveLink_OUT
 - PRemoveLink_OUT
 - hbapiwmi/PRemoveLink_OUT
 - RemoveLink_OUT
 - hbapiwmi/RemoveLink_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - RemoveLink_OUT
---

# _RemoveLink_OUT structure


## -description

The RemoveLink_OUT structure is used by an HBA miniport driver to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removelink">RemoveLink</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the RemoveLink_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-eventcontrol-wmi-class">MSFC_EventControl WMI Class</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removelink">RemoveLink</a>

