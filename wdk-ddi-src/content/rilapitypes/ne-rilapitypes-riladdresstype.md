---
UID: NE:rilapitypes.RILADDRESSTYPE
title: RILADDRESSTYPE
author: windows-driver-content
description: This enumeration describes the RILADDRESSTYPE.
old-location: netvista\riladdresstype.htm
old-project: netvista
ms.assetid: a9fe509e-ef15-49ac-beca-339e3582d16e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_ADDRTYPE_NETWKSPECIFIC, rilapitypes/RIL_ADDRTYPE_EMAIL, rilapitypes/RIL_ADDRTYPE_ALPHANUM, rilapitypes/RIL_ADDRTYPE_IP, RIL_ADDRTYPE_EMAIL, RILADDRESSTYPE, rilapitypes/RIL_ADDRTYPE_NETWKSPECIFIC, rilapitypes/RIL_ADDRTYPE_SUBSCRIBER, RIL_ADDRTYPE_IP, RIL_ADDRTYPE_ABBREV, rilapitypes/RIL_ADDRTYPE_ABBREV, rilapitypes/RILADDRESSTYPE, RILADDRESSTYPE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_ADDRTYPE_NATIONAL, rilapitypes/RIL_ADDRTYPE_UNKNOWN, netvista.riladdresstype, rilapitypes/RIL_ADDRTYPE_INTERNATIONAL, RIL_ADDRTYPE_ALPHANUM, RIL_ADDRTYPE_UNKNOWN, RIL_ADDRTYPE_INTERNATIONAL, RIL_ADDRTYPE_NATIONAL, RIL_ADDRTYPE_SUBSCRIBER
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
-	RILADDRESSTYPE
product: Windows
targetos: Windows
req.typenames: RILADDRESSTYPE
req.product: Windows 10 or later.
---

# RILADDRESSTYPE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSTYPE.




## -syntax


````
enum RILADDRESSTYPE {
  RIL_ADDRTYPE_UNKNOWN        = 0x00000000, 
  RIL_ADDRTYPE_INTERNATIONAL  = 0x00000001, 
  RIL_ADDRTYPE_NATIONAL       = 0x00000002, 
  RIL_ADDRTYPE_NETWKSPECIFIC  = 0x00000003, 
  RIL_ADDRTYPE_SUBSCRIBER     = 0x00000004, 
  RIL_ADDRTYPE_ALPHANUM       = 0x00000005, 
  RIL_ADDRTYPE_ABBREV         = 0x00000006, 
  RIL_ADDRTYPE_IP             = 0x00000007, 
  RIL_ADDRTYPE_EMAIL          = 0x00000008 

};
````


## -enum-fields




### -field RIL_ADDRTYPE_UNKNOWN


### -field RIL_ADDRTYPE_INTERNATIONAL


### -field RIL_ADDRTYPE_NATIONAL


### -field RIL_ADDRTYPE_NETWKSPECIFIC


### -field RIL_ADDRTYPE_SUBSCRIBER


### -field RIL_ADDRTYPE_ALPHANUM


### -field RIL_ADDRTYPE_ABBREV


### -field RIL_ADDRTYPE_IP


### -field RIL_ADDRTYPE_EMAIL


### -field RIL_ADDRTYPE_URI


### -field RIL_ADDRTYPE_MAX




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILADDRESSTYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

