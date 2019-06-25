---
UID: NE:ntddrilapitypes.RILSMSFORMAT
title: RILSMSFORMAT (ntddrilapitypes.h)
description: The RILSMSFORMAT enumeration has the following values.
old-location: netvista\rilsmsformat.htm
tech.root: netvista
ms.assetid: 2552db76-961c-49ce-8b58-90f525e97d29
ms.date: 02/16/2018
ms.keywords: RILSMSFORMAT, RILSMSFORMAT enumeration [Network Drivers Starting with Windows Vista], RIL_SMSFORMAT_3GPP, RIL_SMSFORMAT_3GPP2, RIL_SMSFORMAT_MAX, RIL_SMSFORMAT_NONE, netvista.rilsmsformat, rilapitypes/RILSMSFORMAT, rilapitypes/RIL_SMSFORMAT_3GPP, rilapitypes/RIL_SMSFORMAT_3GPP2, rilapitypes/RIL_SMSFORMAT_MAX, rilapitypes/RIL_SMSFORMAT_NONE
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
- RILSMSFORMAT
product:
- Windows
targetos: Windows
req.typenames: RILSMSFORMAT
---

# RILSMSFORMAT enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>The RILSMSFORMAT enumeration has the following values.


## -syntax


```cpp
enum RILSMSFORMAT  {
  RIL_SMSFORMAT_NONE   = 0,
  RIL_SMSFORMAT_3GPP   = 0x1,
  RIL_SMSFORMAT_3GPP2  = 0x2,
  RIL_SMSFORMAT_MAX    = RIL_SMSFORMAT_3GPP2

};
```


## -enum-fields




### -field RIL_SMSFORMAT_NONE


### -field RIL_SMSFORMAT_3GPP


### -field RIL_SMSFORMAT_3GPP2


### -field RIL_SMSFORMAT_MAX


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


