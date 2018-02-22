---
UID: NE:ntddrilapitypes.RILSYSTEMTYPE
title: RILSYSTEMTYPE
author: windows-driver-content
description: This enumeration represents RILSYSTEMTYPE.
old-location: netvista\rilsystemtype.htm
old-project: netvista
ms.assetid: 5a95969c-d7cd-4afa-affa-7095979ee56b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RIL_SYSTEMTYPE_CDMA, RIL_SYSTEMTYPE_NONE, rilapitypes/RILSYSTEMTYPE, RIL_SYSTEMTYPE_TDSCDMA, RIL_SYSTEMTYPE_LTE, RIL_SYSTEMTYPE_UMTS, rilapitypes/RIL_SYSTEMTYPE_LTE, RILSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_SYSTEMTYPE_GSM, rilapitypes/RIL_SYSTEMTYPE_GSMUMTS, rilapitypes/RIL_SYSTEMTYPE_NONE, RIL_SYSTEMTYPE_ALL, RIL_SYSTEMTYPE_CDMA, RILSYSTEMTYPE, netvista.rilsystemtype, rilapitypes/RIL_SYSTEMTYPE_TDSCDMA, rilapitypes/RIL_SYSTEMTYPE_GSM, rilapitypes/RIL_SYSTEMTYPE_EVDO, RIL_SYSTEMTYPE_GSMUMTS, RIL_SYSTEMTYPE_EVDO, RIL_SYSTEMTYPE_1XRTT, rilapitypes/RIL_SYSTEMTYPE_UMTS, rilapitypes/RIL_SYSTEMTYPE_1XRTT, rilapitypes/RIL_SYSTEMTYPE_ALL
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
-	RILSYSTEMTYPE
product: Windows
targetos: Windows
req.typenames: RILSYSTEMTYPE
---

# RILSYSTEMTYPE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration represents RILSYSTEMTYPE.


## -syntax


````
enum RILSYSTEMTYPE {
  RIL_SYSTEMTYPE_NONE     = 0x00000000, 
  RIL_SYSTEMTYPE_1XRTT    = 0x00000001, 
  RIL_SYSTEMTYPE_EVDO     = 0x00000002, 
  RIL_SYSTEMTYPE_GSM      = 0x00000004, 
  RIL_SYSTEMTYPE_UMTS     = 0x00000008, 
  RIL_SYSTEMTYPE_LTE      = 0x00000010, 
  RIL_SYSTEMTYPE_TDSCDMA  = 0x00000020, 
  RIL_SYSTEMTYPE_CDMA     = RIL_SYSTEMTYPE_1XRTT | RIL_SYSTEMTYPE_EVDO, 
  RIL_SYSTEMTYPE_GSMUMTS  = RIL_SYSTEMTYPE_GSM | RIL_SYSTEMTYPE_UMTS, 
  RIL_SYSTEMTYPE_ALL      = 0x0000003F 

};
````


## -enum-fields




### -field RIL_SYSTEMTYPE_NONE


### -field RIL_SYSTEMTYPE_1XRTT


### -field RIL_SYSTEMTYPE_EVDO


### -field RIL_SYSTEMTYPE_GSM


### -field RIL_SYSTEMTYPE_UMTS


### -field RIL_SYSTEMTYPE_LTE


### -field RIL_SYSTEMTYPE_TDSCDMA


### -field RIL_SYSTEMTYPE_CDMA


### -field RIL_SYSTEMTYPE_GSMUMTS


### -field RIL_SYSTEMTYPE_GSMTDS


### -field RIL_SYSTEMTYPE_GSMUMTSTDS


### -field RIL_SYSTEMTYPE_3GPP


### -field RIL_SYSTEMTYPE_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILSYSTEMTYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

