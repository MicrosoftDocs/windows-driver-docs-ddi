---
UID: NS:hbapiwmi._SetFC3MgmtInfo_OUT
title: _SetFC3MgmtInfo_OUT (hbapiwmi.h)
description: The SetFC3MgmtInfo_OUT structure is used to report the output parameter data of the SetFC3MgmtInfo WMI method to the WMI client.
old-location: storage\setfc3mgmtinfo_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SetFC3MgmtInfo_OUT structure"]
ms.keywords: "*PSetFC3MgmtInfo_OUT, PSetFC3MgmtInfo_OUT, PSetFC3MgmtInfo_OUT structure pointer [Storage Devices], SetFC3MgmtInfo_OUT, SetFC3MgmtInfo_OUT structure [Storage Devices], _SetFC3MgmtInfo_OUT, hbapiwmi/PSetFC3MgmtInfo_OUT, hbapiwmi/SetFC3MgmtInfo_OUT, storage.setfc3mgmtinfo_out, structs-Fibre_86907ae9-a0a0-4836-a822-d07cd2adfdb0.xml"
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
req.typenames: SetFC3MgmtInfo_OUT, *PSetFC3MgmtInfo_OUT
f1_keywords:
 - _SetFC3MgmtInfo_OUT
 - hbapiwmi/_SetFC3MgmtInfo_OUT
 - PSetFC3MgmtInfo_OUT
 - hbapiwmi/PSetFC3MgmtInfo_OUT
 - SetFC3MgmtInfo_OUT
 - hbapiwmi/SetFC3MgmtInfo_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SetFC3MgmtInfo_OUT
 - PSetFC3MgmtInfo_OUT
 - SetFC3MgmtInfo_OUT
---

# _SetFC3MgmtInfo_OUT structure


## -description

The SetFC3MgmtInfo_OUT structure is used to report the output parameter data of the <a href="/windows-hardware/drivers/storage/setfc3mgmtinfo">SetFC3MgmtInfo</a> WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the SetFC3MgmtInfo_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.

## -see-also

<a href="/windows-hardware/drivers/storage/setfc3mgmtinfo">SetFC3MgmtInfo</a>

