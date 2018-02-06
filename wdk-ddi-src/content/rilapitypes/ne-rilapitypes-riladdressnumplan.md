---
UID: NE:rilapitypes.RILADDRESSNUMPLAN
title: RILADDRESSNUMPLAN
author: windows-driver-content
description: This enumeration describes the RILADDRESSNUMPLAN.
old-location: netvista\riladdressnumplan.htm
old-project: netvista
ms.assetid: fa25ce95-3eed-41f3-a0eb-5c290fa032e8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_NUMPLAN_NATIONAL, RIL_NUMPLAN_TELEPHONE, rilapitypes/RIL_NUMPLAN_ERMES, RILADDRESSNUMPLAN, RIL_NUMPLAN_PRIVATE, RIL_NUMPLAN_ERMES, RIL_NUMPLAN_DATA, rilapitypes/RIL_NUMPLAN_TELEX, rilapitypes/RILADDRESSNUMPLAN, netvista.riladdressnumplan, RILADDRESSNUMPLAN enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_NUMPLAN_DATA, rilapitypes/RIL_NUMPLAN_TELEPHONE, RIL_NUMPLAN_UNKNOWN, rilapitypes/RIL_NUMPLAN_PRIVATE, RIL_NUMPLAN_NATIONAL, RIL_NUMPLAN_TELEX, rilapitypes/RIL_NUMPLAN_UNKNOWN
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
-	RILADDRESSNUMPLAN
product: Windows
targetos: Windows
req.typenames: RILADDRESSNUMPLAN
req.product: Windows 10 or later.
---

# RILADDRESSNUMPLAN enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSNUMPLAN.




## -syntax


````
enum RILADDRESSNUMPLAN {
  RIL_NUMPLAN_UNKNOWN    = 0x00000000, 
  RIL_NUMPLAN_TELEPHONE  = 0x00000001, 
  RIL_NUMPLAN_DATA       = 0x00000002, 
  RIL_NUMPLAN_TELEX      = 0x00000003, 
  RIL_NUMPLAN_NATIONAL   = 0x00000004, 
  RIL_NUMPLAN_PRIVATE    = 0x00000005, 
  RIL_NUMPLAN_ERMES      = 0x00000006 

};
````


## -enum-fields




### -field RIL_NUMPLAN_UNKNOWN



### -field RIL_NUMPLAN_TELEPHONE



### -field RIL_NUMPLAN_DATA



### -field RIL_NUMPLAN_TELEX



### -field RIL_NUMPLAN_NATIONAL



### -field RIL_NUMPLAN_PRIVATE



### -field RIL_NUMPLAN_ERMES



### -field RIL_NUMPLAN_MAX




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESSNUMPLAN enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

