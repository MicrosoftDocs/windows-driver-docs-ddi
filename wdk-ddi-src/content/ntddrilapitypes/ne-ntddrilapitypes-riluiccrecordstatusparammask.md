---
UID: NE:ntddrilapitypes.RILUICCRECORDSTATUSPARAMMASK
title: RILUICCRECORDSTATUSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILUICCRECORDSTATUSPARAMMASK.
old-location: netvista\riluiccrecordstatusparammask.htm
tech.root: netvista
ms.assetid: 6db3cdd2-3865-42d7-8b63-3dcacaec5941
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCRECORDSTATUSPARAMMASK, RILUICCRECORDSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_URS_ALL, RIL_PARAM_URS_FILELOCKSTATUS, RIL_PARAM_URS_ITEMCOUNT, RIL_PARAM_URS_RECORDTYPE, RIL_PARAM_URS_SIZE, netvista.riluiccrecordstatusparammask, rilapitypes/RILUICCRECORDSTATUSPARAMMASK, rilapitypes/RIL_PARAM_URS_ALL, rilapitypes/RIL_PARAM_URS_FILELOCKSTATUS, rilapitypes/RIL_PARAM_URS_ITEMCOUNT, rilapitypes/RIL_PARAM_URS_RECORDTYPE, rilapitypes/RIL_PARAM_URS_SIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
-	rilapitypes.h
api_name:
-	RILUICCRECORDSTATUSPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILUICCRECORDSTATUSPARAMMASK
---

# RILUICCRECORDSTATUSPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCRECORDSTATUSPARAMMASK.


## -syntax


```
enum RILUICCRECORDSTATUSPARAMMASK {
  RIL_PARAM_URS_RECORDTYPE      = 0x00000001,
  RIL_PARAM_URS_ITEMCOUNT       = 0x00000002,
  RIL_PARAM_URS_SIZE            = 0x00000004,
  RIL_PARAM_URS_FILELOCKSTATUS  = 0x00000008,
  RIL_PARAM_URS_ALL             = 0x0000000F

};
```


## -enum-fields




### -field RIL_PARAM_URS_RECORDTYPE


### -field RIL_PARAM_URS_ITEMCOUNT


### -field RIL_PARAM_URS_SIZE


### -field RIL_PARAM_URS_FILELOCKSTATUS


### -field RIL_PARAM_URS_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


