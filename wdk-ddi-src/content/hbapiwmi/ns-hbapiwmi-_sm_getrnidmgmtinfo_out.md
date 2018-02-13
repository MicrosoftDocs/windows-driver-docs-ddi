---
UID: NS:hbapiwmi._SM_GetRNIDMgmtInfo_OUT
title: "_SM_GetRNIDMgmtInfo_OUT"
author: windows-driver-content
description: The SM_GetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_GetRNIDMgmtInfo method.
old-location: storage\sm_getrnidmgmtinfo_out.htm
old-project: storage
ms.assetid: e12bd494-4d2a-44a9-95dc-0bc78fa73a97
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SM_GetRNIDMgmtInfo_OUT structure [Storage Devices], PSM_GetRNIDMgmtInfo_OUT, PSM_GetRNIDMgmtInfo_OUT structure pointer [Storage Devices], structs-Fibre_c5f33dc4-bde0-43bb-8528-9cb2e0d2ee3f.xml, hbapiwmi/PSM_GetRNIDMgmtInfo_OUT, hbapiwmi/SM_GetRNIDMgmtInfo_OUT, storage.sm_getrnidmgmtinfo_out, _SM_GetRNIDMgmtInfo_OUT, *PSM_GetRNIDMgmtInfo_OUT, SM_GetRNIDMgmtInfo_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SM_GetRNIDMgmtInfo_OUT
product: Windows
targetos: Windows
req.typenames: "*PSM_GetRNIDMgmtInfo_OUT, SM_GetRNIDMgmtInfo_OUT"
---

# _SM_GetRNIDMgmtInfo_OUT structure


## -description


The SM_GetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_GetRNIDMgmtInfo method.


## -syntax


````
typedef struct _SM_GetRNIDMgmtInfo_OUT {
  ULONG          HBAStatus;
  HBAFC3MgmtInfo MgmtInfo;
} SM_GetRNIDMgmtInfo_OUT, *PSM_GetRNIDMgmtInfo_OUT;
````


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field MgmtInfo

A structure of type HBAFC3MgmtInfo that holds FC3 management information. The FC3 management information is used to configure the fibre channel adapter.


## -remarks



The WMI tool suite generates a declaration of the SM_GetRNIDMgmtInfo_OUTstructure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



