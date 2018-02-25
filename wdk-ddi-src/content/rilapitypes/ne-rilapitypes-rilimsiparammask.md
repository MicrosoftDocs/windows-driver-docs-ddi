---
UID: NE:rilapitypes.RILIMSIPARAMMASK
title: RILIMSIPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILIMSIPARAMMASK.
old-location: netvista\rilimsiparammask.htm
old-project: netvista
ms.assetid: 8fe1ecda-4b2f-4a6f-b02c-7e50630614eb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, I, K, L, M, P, R, RILIMSIPARAMMASK, RILIMSIPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_IMSI_ALL, RIL_PARAM_IMSI_IMSI, RIL_PARAM_IMSI_MCC, RIL_PARAM_IMSI_MNC, S, netvista.rilimsiparammask, rilapitypes/RILIMSIPARAMMASK, rilapitypes/RIL_PARAM_IMSI_ALL, rilapitypes/RIL_PARAM_IMSI_IMSI, rilapitypes/RIL_PARAM_IMSI_MCC, rilapitypes/RIL_PARAM_IMSI_MNC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
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
-	RILIMSIPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILIMSIPARAMMASK
req.product: Windows 10 or later.
---

# RILIMSIPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILIMSIPARAMMASK.




## -syntax


````
enum RILIMSIPARAMMASK {
  RIL_PARAM_IMSI_IMSI  = 0x00000001, 
  RIL_PARAM_IMSI_MCC   = 0x00000002, 
  RIL_PARAM_IMSI_MNC   = 0x00000004, 
  RIL_PARAM_IMSI_ALL   = 0x00000007 

};
````


## -enum-fields




### -field RIL_PARAM_IMSI_IMSI


### -field RIL_PARAM_IMSI_MCC


### -field RIL_PARAM_IMSI_MNC


### -field RIL_PARAM_IMSI_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSIPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

