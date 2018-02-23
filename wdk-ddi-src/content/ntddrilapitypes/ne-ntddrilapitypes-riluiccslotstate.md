---
UID: NE:ntddrilapitypes.RILUICCSLOTSTATE
title: RILUICCSLOTSTATE
author: windows-driver-content
description: This enumeration describes the RILUICCSLOTSTATE.
old-location: netvista\riluiccslotstate.htm
old-project: netvista
ms.assetid: e88c6e79-c1a0-4ff9-ac00-f8f367aaa7c4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_UICCSLOT_OFF, RIL_UICCSLOT_NOT_READY, RIL_UICCSLOT_OFF_EMPTY, RIL_UICCSLOT_ERROR, RIL_UICCSLOT_ACTIVE, rilapitypes/RIL_UICCSLOT_ACTIVE, RILUICCSLOTSTATE, RILUICCSLOTSTATE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILUICCSLOTSTATE, RIL_UICCSLOT_EMPTY, netvista.riluiccslotstate, rilapitypes/RIL_UICCSLOT_OFF_EMPTY, rilapitypes/RIL_UICCSLOT_NOT_READY, rilapitypes/RIL_UICCSLOT_OFF, rilapitypes/RIL_UICCSLOT_ERROR, rilapitypes/RIL_UICCSLOT_EMPTY
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
-	RILUICCSLOTSTATE
product: Windows
targetos: Windows
req.typenames: RILUICCSLOTSTATE
---

# RILUICCSLOTSTATE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCSLOTSTATE.


## -syntax


````
enum RILUICCSLOTSTATE {
  RIL_UICCSLOT_OFF_EMPTY  = 0x01, 
  RIL_UICCSLOT_OFF        = 0x02, 
  RIL_UICCSLOT_EMPTY      = 0x03, 
  RIL_UICCSLOT_NOT_READY  = 0x04, 
  RIL_UICCSLOT_ACTIVE     = 0x05, 
  RIL_UICCSLOT_ERROR      = 0x06 

};
````


## -enum-fields




### -field RIL_UICCSLOT_OFF_EMPTY


### -field RIL_UICCSLOT_OFF


### -field RIL_UICCSLOT_EMPTY


### -field RIL_UICCSLOT_NOT_READY


### -field RIL_UICCSLOT_ACTIVE


### -field RIL_UICCSLOT_ERROR


### -field RIL_UICCSLOT_MAX




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCSLOTSTATE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

