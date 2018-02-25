---
UID: NE:ntddrilapitypes.RILPOSITIONINFOTDSCDMAPARAMMASK
title: RILPOSITIONINFOTDSCDMAPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILPOSITIONINFOTDSCDMAPARAMMASK.
old-location: netvista\rilpositioninfotdscdmaparammask.htm
old-project: netvista
ms.assetid: bbd7579f-ff94-412a-8472-b8e6370f7195
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, C, D, F, I, K, L, M, N, O, P, R, RILPOSITIONINFOTDSCDMAPARAMMASK, RILPOSITIONINFOTDSCDMAPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_TDSCDMA_ALL, RIL_PARAM_POSITION_TDSCDMA_CELLID, RIL_PARAM_POSITION_TDSCDMA_CELLPARAM, RIL_PARAM_POSITION_TDSCDMA_LAC, RIL_PARAM_POSITION_TDSCDMA_MCC, RIL_PARAM_POSITION_TDSCDMA_MNC, RIL_PARAM_POSITION_TDSCDMA_PATHLOSS, RIL_PARAM_POSITION_TDSCDMA_RSCP, RIL_PARAM_POSITION_TDSCDMA_TA, RIL_PARAM_POSITION_TDSCDMA_UARFCN, S, T, netvista.rilpositioninfotdscdmaparammask, rilapitypes/ RIL_PARAM_POSITION_TDSCDMA_RSCP, rilapitypes/RILPOSITIONINFOTDSCDMAPARAMMASK, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_ALL, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_CELLID, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_CELLPARAM, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_LAC, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_MCC, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_MNC, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_PATHLOSS, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_TA, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_UARFCN"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPOSITIONINFOTDSCDMAPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFOTDSCDMAPARAMMASK
---

# RILPOSITIONINFOTDSCDMAPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILPOSITIONINFOTDSCDMAPARAMMASK.




## -syntax


````
enum RILPOSITIONINFOTDSCDMAPARAMMASK {
  RIL_PARAM_POSITION_TDSCDMA_MCC        = 0x00000001, 
  RIL_PARAM_POSITION_TDSCDMA_MNC        = 0x00000002, 
  RIL_PARAM_POSITION_TDSCDMA_LAC        = 0x00000004, 
  RIL_PARAM_POSITION_TDSCDMA_CELLID     = 0x00000008, 
  RIL_PARAM_POSITION_TDSCDMA_UARFCN     = 0x00000010, 
  RIL_PARAM_POSITION_TDSCDMA_CELLPARAM  = 0x00000020, 
  RIL_PARAM_POSITION_TDSCDMA_TA         = 0x00000040, 
   RIL_PARAM_POSITION_TDSCDMA_RSCP      = 0x00000080, 
  RIL_PARAM_POSITION_TDSCDMA_PATHLOSS   = 0x00000100, 
  RIL_PARAM_POSITION_TDSCDMA_ALL        = 0x000001ff 

};
````


## -enum-fields




### -field RIL_PARAM_POSITION_TDSCDMA_MCC


### -field RIL_PARAM_POSITION_TDSCDMA_MNC


### -field RIL_PARAM_POSITION_TDSCDMA_LAC


### -field RIL_PARAM_POSITION_TDSCDMA_CELLID


### -field RIL_PARAM_POSITION_TDSCDMA_UARFCN


### -field RIL_PARAM_POSITION_TDSCDMA_CELLPARAM


### -field RIL_PARAM_POSITION_TDSCDMA_TA


### -field RIL_PARAM_POSITION_TDSCDMA_RSCP


### -field RIL_PARAM_POSITION_TDSCDMA_PATHLOSS


### -field RIL_PARAM_POSITION_TDSCDMA_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOTDSCDMAPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

