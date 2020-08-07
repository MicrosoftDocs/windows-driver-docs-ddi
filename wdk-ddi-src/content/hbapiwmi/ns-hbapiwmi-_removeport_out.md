---
UID: NS:hbapiwmi._RemovePort_OUT
title: _RemovePort_OUT (hbapiwmi.h)
description: The RemovePort_OUT structure is used by an HBA miniport driver to the output parameter data of the RemovePort WMI method to the WMI client.
old-location: storage\removeport_out.htm
tech.root: storage
ms.assetid: 89cb75e4-5e3b-4277-b173-abed00a7360b
ms.date: 03/29/2018
keywords: ["RemovePort_OUT structure"]
ms.keywords: "*PRemovePort_OUT, PRemovePort_OUT, PRemovePort_OUT structure pointer [Storage Devices], RemovePort_OUT, RemovePort_OUT structure [Storage Devices], _RemovePort_OUT, hbapiwmi/PRemovePort_OUT, hbapiwmi/RemovePort_OUT, storage.removeport_out, structs-Fibre_dc8be161-745b-4919-9227-e333933482cf.xml"
f1_keywords:
 - "hbapiwmi/RemovePort_OUT"
 - "RemovePort_OUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- RemovePort_OUT
targetos: Windows
req.typenames: RemovePort_OUT, *PRemovePort_OUT
---

# _RemovePort_OUT structure


## -description


The RemovePort_OUT structure is used by an HBA miniport driver to the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removeport">RemovePort</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>. 


## -remarks



The WMI tool suite generates a declaration of the RemovePort_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-eventcontrol-wmi-class">MSFC_EventControl WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/removeport">RemovePort</a>
 

 

