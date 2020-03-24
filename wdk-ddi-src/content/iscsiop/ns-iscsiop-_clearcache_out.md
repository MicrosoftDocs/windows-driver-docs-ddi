---
UID: NS:iscsiop._ClearCache_OUT
title: _ClearCache_OUT (iscsiop.h)
description: The ClearCache_OUT structure holds the output data for the ClearCache method.
old-location: storage\clearcache_out.htm
tech.root: storage
ms.assetid: ab97d0b0-00fc-499c-9b1b-83731fe8e935
ms.date: 03/29/2018
keywords: ["_ClearCache_OUT structure"]
ms.keywords: "*PClearCache_OUT, ClearCache_OUT, ClearCache_OUT structure [Storage Devices], PClearCache_OUT, PClearCache_OUT structure pointer [Storage Devices], _ClearCache_OUT, iscsiop/ClearCache_OUT, iscsiop/PClearCache_OUT, storage.clearcache_out, structs-iSCSI_e96c134a-dfb1-474a-b730-1fb6e8d8f86f.xml"
f1_keywords:
 - "iscsiop/ClearCache_OUT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- ClearCache_OUT
product:
- Windows
targetos: Windows
req.typenames: ClearCache_OUT, *PClearCache_OUT
---

# _ClearCache_OUT structure


## -description


The ClearCache_OUT structure holds the output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/clearcache">ClearCache</a> method.


## -struct-fields




### -field Status

On output from <b>ClearCache</b>, the status of the <b>ClearCache</b> operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/clearcache">ClearCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-securityconfigoperations-wmi-class">MSiSCSI_SecurityConfigOperations WMI Class</a>
 

 

