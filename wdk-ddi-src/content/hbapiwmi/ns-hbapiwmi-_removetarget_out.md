---
UID: NS:hbapiwmi._RemoveTarget_OUT
title: "_RemoveTarget_OUT"
author: windows-driver-content
description: The RemoveTarget_OUT structure is used by an HBA miniport driver to report the output parameter data of the RemoveTarget WMI method to the WMI client.
old-location: storage\removetarget_out.htm
tech.root: storage
ms.assetid: 176dbb0c-227e-48b2-956c-9e2b42f4c68b
ms.date: 03/29/2018
ms.keywords: "*PRemoveTarget_OUT, PRemoveTarget_OUT, PRemoveTarget_OUT structure pointer [Storage Devices], RemoveTarget_OUT, RemoveTarget_OUT structure [Storage Devices], _RemoveTarget_OUT, hbapiwmi/PRemoveTarget_OUT, hbapiwmi/RemoveTarget_OUT, storage.removetarget_out, structs-Fibre_0cab8f87-0c96-4e03-bfd9-495e245850ca.xml"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	RemoveTarget_OUT
product:
- Windows
targetos: Windows
req.typenames: RemoveTarget_OUT, *PRemoveTarget_OUT
---

# _RemoveTarget_OUT structure


## -description


The RemoveTarget_OUT structure is used by an HBA miniport driver to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564030">RemoveTarget</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


## -remarks



The WMI tool suite generates a declaration of the RemoveTarget_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562490">MSFC_EventControl WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564030">RemoveTarget</a>
 

 

