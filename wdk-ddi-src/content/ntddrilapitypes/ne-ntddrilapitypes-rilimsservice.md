---
UID: NE:ntddrilapitypes.RILIMSSERVICE
title: RILIMSSERVICE (ntddrilapitypes.h)
description: The RILIMSSERVICE enumeration has the following values.
old-location: netvista\rilimsservice.htm
tech.root: netvista
ms.assetid: 11d009d7-5a97-46a8-b1d6-f1906127bf3a
ms.date: 02/16/2018
ms.keywords: RILIMSSERVICE, RILIMSSERVICE enumeration [Network Drivers Starting with Windows Vista], RIL_IMS_SERVICE_ALL, RIL_IMS_SERVICE_CUSTOM, RIL_IMS_SERVICE_SMS, RIL_IMS_SERVICE_VIDEO, RIL_IMS_SERVICE_VOICE, netvista.rilimsservice, rilapitypes/RILIMSSERVICE, rilapitypes/RIL_IMS_SERVICE_ALL, rilapitypes/RIL_IMS_SERVICE_CUSTOM, rilapitypes/RIL_IMS_SERVICE_SMS, rilapitypes/RIL_IMS_SERVICE_VIDEO, rilapitypes/RIL_IMS_SERVICE_VOICE
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILIMSSERVICE
product:
- Windows
targetos: Windows
req.typenames: RILIMSSERVICE
---

# RILIMSSERVICE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>The RILIMSSERVICE enumeration has the following values.


## -syntax


```cpp
enum RILIMSSERVICE  {
  RIL_IMS_SERVICE_SMS     = 0x00000001,
  RIL_IMS_SERVICE_VOICE   = 0x00000002,
  RIL_IMS_SERVICE_VIDEO   = 0x00000004,
  RIL_IMS_SERVICE_CUSTOM  = 0x00000008,
  RIL_IMS_SERVICE_ALL     = 0x0000000F

};
```


## -enum-fields




### -field RIL_IMS_SERVICE_SMS


### -field RIL_IMS_SERVICE_VOICE


### -field RIL_IMS_SERVICE_VIDEO


### -field RIL_IMS_SERVICE_CUSTOM


### -field RIL_IMS_SERVICE_SUPSVC


### -field RIL_IMS_SERVICE_RCS


### -field RIL_IMS_SERVICE_USSD


### -field RIL_IMS_SERVICE_E_VOICE


### -field RIL_IMS_SERVICE_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


