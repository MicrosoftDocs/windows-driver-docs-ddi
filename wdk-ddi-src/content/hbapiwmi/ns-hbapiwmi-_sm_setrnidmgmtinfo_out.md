---
UID: NS:hbapiwmi._SM_SetRNIDMgmtInfo_OUT
title: _SM_SetRNIDMgmtInfo_OUT (hbapiwmi.h)
description: The SM_SetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_SetRNIDMgmtInfo method.
old-location: storage\sm_setrnidmgmtinfo_out.htm
tech.root: storage
ms.assetid: 30bb4e82-3a51-4d58-87aa-2e1545a9244f
ms.date: 03/29/2018
ms.keywords: "*PSM_SetRNIDMgmtInfo_OUT, PSM_SetRNIDMgmtInfo_OUT, PSM_SetRNIDMgmtInfo_OUT structure pointer [Storage Devices], SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT structure [Storage Devices], _SM_SetRNIDMgmtInfo_OUT, hbapiwmi/PSM_SetRNIDMgmtInfo_OUT, hbapiwmi/SM_SetRNIDMgmtInfo_OUT, storage.sm_setrnidmgmtinfo_out, structs-Fibre_c416e571-7970-4856-937a-a8bd546d8d3d.xml"
f1_keywords:
 - "hbapiwmi/SM_SetRNIDMgmtInfo_OUT"
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
- SM_SetRNIDMgmtInfo_OUT
product:
- Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# _SM_SetRNIDMgmtInfo_OUT structure


## -description


The SM_SetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_SetRNIDMgmtInfo method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.


## -remarks



The WMI tool suite generates a declaration of the SM_SetRNIDMgmtInfo_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



