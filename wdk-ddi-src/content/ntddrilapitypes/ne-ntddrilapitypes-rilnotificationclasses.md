---
UID: NE:ntddrilapitypes.RILNOTIFICATIONCLASSES
title: RILNOTIFICATIONCLASSES
author: windows-driver-content
description: This enumeration describes the RILNOTIFICATIONCLASSES.
old-location: netvista\rilnotificationclasses.htm
old-project: netvista
ms.assetid: f61fc609-40ca-40eb-a877-88c73cf3506e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilnotificationclasses, RIL_NCLASS_NOTIFICATIONS, rilapitypes/RIL_NCLASS_FUNCRESULT, RILNOTIFICATIONCLASSES enumeration [Network Drivers Starting with Windows Vista], RILNOTIFICATIONCLASSES, rilapitypes/RILNOTIFICATIONCLASSES, RIL_NCLASS_FUNCRESULT, rilapitypes/RIL_NCLASS_NOTIFICATIONS
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
-	RILNOTIFICATIONCLASSES
product: Windows
targetos: Windows
req.typenames: RILNOTIFICATIONCLASSES
---

# RILNOTIFICATIONCLASSES enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILNOTIFICATIONCLASSES. 




## -syntax


````
enum RILNOTIFICATIONCLASSES {
  RIL_NCLASS_FUNCRESULT     = 0x00000000, 
  RIL_NCLASS_NOTIFICATIONS  = 0x10000000 

};
````


## -enum-fields




### -field RIL_NCLASS_FUNCRESULT


### -field RIL_NCLASS_NOTIFICATIONS


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILNOTIFICATIONCLASSES enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

