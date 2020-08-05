---
UID: NS:hbapiwmi._AddLink_OUT
title: _AddLink_OUT (hbapiwmi.h)
description: The AddLink_OUT structure is used by an HBA miniport driver to report the status of a call to the AddLink WMI method.
old-location: storage\addlink_out.htm
tech.root: storage
ms.assetid: fe088ec7-2577-488d-a1c7-a7e2a1f86f6a
ms.date: 03/29/2018
keywords: ["AddLink_OUT structure"]
ms.keywords: "*PAddLink_OUT, AddLink_OUT, AddLink_OUT structure [Storage Devices], PAddLink_OUT, PAddLink_OUT structure pointer [Storage Devices], _AddLink_OUT, hbapiwmi/AddLink_OUT, hbapiwmi/PAddLink_OUT, storage.addlink_out, structs-Fibre_5f49a86f-a59f-4572-bfa2-5bb78dfe599b.xml"
f1_keywords:
 - "hbapiwmi/AddLink_OUT"
 - "AddLink_OUT"
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
- AddLink_OUT
targetos: Windows
req.typenames: AddLink_OUT, *PAddLink_OUT
---

# _AddLink_OUT structure


## -description


The AddLink_OUT structure is used by an HBA miniport driver to report the status of a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addlink">AddLink</a> WMI method.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a> that indicates the result of an HBA query operation.


## -remarks



The WMI tool suite generates a declaration of the AddLink_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-eventcontrol-wmi-class">MSFC_EventControl WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addlink">AddLink</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-eventcontrol-wmi-class">MSFC_EventControl WMI Class</a>
 

 

