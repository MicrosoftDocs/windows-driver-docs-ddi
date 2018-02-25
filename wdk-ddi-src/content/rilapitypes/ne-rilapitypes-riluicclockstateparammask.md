---
UID: NE:rilapitypes.RILUICCLOCKSTATEPARAMMASK
title: RILUICCLOCKSTATEPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILUICCLOCKSTATEPARAMMASK.
old-location: netvista\riluicclockstateparammask.htm
old-project: netvista
ms.assetid: 19366fbe-8a04-4a9f-9acc-8de0211e6e0d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, C, E, I, K, L, M, O, P, R, RILUICCLOCKSTATEPARAMMASK, RILUICCLOCKSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UICCLOCKSTATE_ALL, RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, RIL_PARAM_UICCLOCKSTATE_UICCLOCK, RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT, RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT, S, T, U, netvista.riluicclockstateparammask, rilapitypes/RILUICCLOCKSTATEPARAMMASK, rilapitypes/RIL_PARAM_UICCLOCKSTATE_ALL, rilapitypes/RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, rilapitypes/RIL_PARAM_UICCLOCKSTATE_UICCLOCK, rilapitypes/RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT, rilapitypes/RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT"
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
-	RILUICCLOCKSTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCLOCKSTATEPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCLOCKSTATEPARAMMASK.


## -syntax


````
enum RILUICCLOCKSTATEPARAMMASK {
  RIL_PARAM_UICCLOCKSTATE_UICCLOCK             = 0x00000001, 
  RIL_PARAM_UICCLOCKSTATE_LOCKSTATE            = 0x00000002, 
  RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT   = 0x00000004, 
  RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT  = 0x00000008, 
  RIL_PARAM_UICCLOCKSTATE_ALL                  = 0x0000000F 

};
````


## -enum-fields




### -field RIL_PARAM_UICCLOCKSTATE_UICCLOCK


### -field RIL_PARAM_UICCLOCKSTATE_LOCKSTATE


### -field RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT


### -field RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT


### -field RIL_PARAM_UICCLOCKSTATE_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCLOCKSTATEPARAMMASK enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

