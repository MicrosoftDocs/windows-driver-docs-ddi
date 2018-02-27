---
UID: NE:ntddrilapitypes.RILADDRESSPARAMMASK
title: RILADDRESSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILADDRESSPARAMMASK enumeration.
old-location: netvista\riladdressparammask.htm
old-project: netvista
ms.assetid: 02d77f8f-9327-40e4-b38b-7f1a02abf4b1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILADDRESSPARAMMASK, RILADDRESSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_A_ADDRESS, RIL_PARAM_A_ALL, RIL_PARAM_A_NONE, RIL_PARAM_A_NUMPLAN, RIL_PARAM_A_TYPE, netvista.riladdressparammask, rilapitypes/RILADDRESSPARAMMASK, rilapitypes/RIL_PARAM_A_ADDRESS, rilapitypes/RIL_PARAM_A_ALL, rilapitypes/RIL_PARAM_A_NONE, rilapitypes/RIL_PARAM_A_NUMPLAN, rilapitypes/RIL_PARAM_A_TYPE
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
-	RILADDRESSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILADDRESSPARAMMASK
---

# RILADDRESSPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSPARAMMASK enumeration.


## -syntax


````
enum RILADDRESSPARAMMASK {
  RIL_PARAM_A_NONE     = 0x00000000, 
  RIL_PARAM_A_TYPE     = 0x00000001, 
  RIL_PARAM_A_NUMPLAN  = 0x00000002, 
  RIL_PARAM_A_ADDRESS  = 0x00000004, 
  RIL_PARAM_A_ALL      = 0x00000007 

};
````


## -enum-fields




### -field RIL_PARAM_A_NONE


### -field RIL_PARAM_A_TYPE


### -field RIL_PARAM_A_NUMPLAN


### -field RIL_PARAM_A_ADDRESS


### -field RIL_PARAM_A_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESSPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

