---
UID: NE:rilapitypes.RILUICCLOCKSTATELOCKSTATE
title: RILUICCLOCKSTATELOCKSTATE
author: windows-driver-content
description: This enumeration describes the RILUICCLOCKSTATELOCKSTATE.
old-location: netvista\riluicclockstatelockstate.htm
old-project: netvista
ms.assetid: 95f73081-b809-407d-b73b-975b97301449
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_UICCLOCKSTATE_BLOCKED, RIL_UICCLOCKSTATE_BLOCKED, RIL_UICCLOCKSTATE_VERIFIED, RILUICCLOCKSTATELOCKSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCLOCKSTATE_ENABLED, rilapitypes/RIL_UICCLOCKSTATE_ENABLED, rilapitypes/RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, rilapitypes/RIL_UICCLOCKSTATE_VERIFIED, rilapitypes/RILUICCLOCKSTATELOCKSTATE, RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, RILUICCLOCKSTATELOCKSTATE, netvista.riluicclockstatelockstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILUICCLOCKSTATELOCKSTATE
product: Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATELOCKSTATE
req.product: Windows 10 or later.
---

# RILUICCLOCKSTATELOCKSTATE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCLOCKSTATELOCKSTATE.


## -syntax


````
enum RILUICCLOCKSTATELOCKSTATE {
  RIL_PARAM_UICCLOCKSTATE_LOCKSTATE  = 0x0000000, 
  RIL_UICCLOCKSTATE_VERIFIED         = 0x0000001, 
  RIL_UICCLOCKSTATE_ENABLED          = 0x0000002, 
  RIL_UICCLOCKSTATE_BLOCKED          = 0x0000003 

};
````


## -enum-fields




### -field RIL_UICCLOCKSTATE_NONE



#### - RIL_UICCLOCKSTATE_VERIFIED

Lock is verified.


#### - RIL_UICCLOCKSTATE_ENABLED

Lock is enabled.


#### - RIL_UICCLOCKSTATE_BLOCKED

Lock is blocked.


### -field RIL_UICCLOCKSTATE_ALL




#### - RIL_PARAM_UICCLOCKSTATE_LOCKSTATE

None of the other state bits are set.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCLOCKSTATELOCKSTATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

