---
UID: NE:ntddrilapitypes.RILSUBSCRIBERINFOPARAMMASK
title: RILSUBSCRIBERINFOPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILSUBSCRIBERINFOPARAMMASK.
old-location: netvista\rilsubscriberinfoparammask.htm
old-project: netvista
ms.assetid: 271492ee-9053-4150-9e31-f121c9a94097
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSUBSCRIBERINFOPARAMMASK, RILSUBSCRIBERINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_SI_DESCRIPTION, rilapitypes/RIL_PARAM_SI_SERVICE, RIL_PARAM_SI_ALL, rilapitypes/RIL_PARAM_SI_ADDRESS, RIL_PARAM_SI_DESCRIPTION, RIL_PARAM_SI_SERVICE, rilapitypes/RIL_PARAM_SI_ALL, netvista.rilsubscriberinfoparammask, rilapitypes/RILSUBSCRIBERINFOPARAMMASK, RIL_PARAM_SI_ADDRESS
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
-	RILSUBSCRIBERINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSUBSCRIBERINFOPARAMMASK
---

# RILSUBSCRIBERINFOPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILSUBSCRIBERINFOPARAMMASK.


## -syntax


````
enum RILSUBSCRIBERINFOPARAMMASK {
  RIL_PARAM_SI_ADDRESS      = 0x00000001, 
  RIL_PARAM_SI_DESCRIPTION  = 0x00000002, 
  RIL_PARAM_SI_SERVICE      = 0x00000004, 
  RIL_PARAM_SI_ALL          = 0x00000007 

};
````


## -enum-fields




### -field RIL_PARAM_SI_ADDRESS


### -field RIL_PARAM_SI_DESCRIPTION


### -field RIL_PARAM_SI_SERVICE


### -field RIL_PARAM_SI_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILSUBSCRIBERINFOPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

