---
UID: NE:rilapitypes.RILIMSSYSTEMTYPE
title: RILIMSSYSTEMTYPE
author: windows-driver-content
description: The RILIMSSYSTEMTYPE enumeration has the following values.
old-location: netvista\rilimssystemtype.htm
old-project: netvista
ms.assetid: e1f5dde2-8e45-4904-bbf3-bd2358f95a5b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILIMSSYSTEMTYPE, RILIMSSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSYSTEMTYPE_LTE, RIL_IMSSYSTEMTYPE_MAX, RIL_IMSSYSTEMTYPE_UNKNOWN, RIL_IMSSYSTEMTYPE_WIFI, netvista.rilimssystemtype, rilapitypes/RILIMSSYSTEMTYPE, rilapitypes/RIL_IMSSYSTEMTYPE_LTE, rilapitypes/RIL_IMSSYSTEMTYPE_MAX, rilapitypes/RIL_IMSSYSTEMTYPE_UNKNOWN, rilapitypes/RIL_IMSSYSTEMTYPE_WIFI
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILIMSSYSTEMTYPE
product: Windows
targetos: Windows
req.typenames: RILIMSSYSTEMTYPE
req.product: Windows 10 or later.
---

# RILIMSSYSTEMTYPE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>The RILIMSSYSTEMTYPE enumeration has the following values.




## -syntax


````
enum RILIMSSYSTEMTYPE {
  RIL_IMSSYSTEMTYPE_UNKNOWN  = 0x00000000, 
  RIL_IMSSYSTEMTYPE_WIFI     = 0x00000001, 
  RIL_IMSSYSTEMTYPE_LTE      = 0x00000002, 
  RIL_IMSSYSTEMTYPE_MAX      = RIL_IMSSYSTEMTYPE_LTE 

};
````


## -enum-fields




### -field RIL_IMSSYSTEMTYPE_UNKNOWN


### -field RIL_IMSSYSTEMTYPE_WIFI


### -field RIL_IMSSYSTEMTYPE_LTE


### -field RIL_IMSSYSTEMTYPE_MAX


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSSYSTEMTYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

