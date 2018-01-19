---
UID: NE:rilapitypes.RILOPERATORNAMESPARAMMASK
title: RILOPERATORNAMESPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILOPERATORNAMESPARAMMASK.
old-location: netvista\riloperatornamesparammask.htm
old-project: netvista
ms.assetid: f3e3654f-d317-4a8c-aa18-bbac86b06286
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILOPERATORNAMESPARAMMASK, RILOPERATORNAMESPARAMMASK
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
req.alt-api: RILOPERATORNAMESPARAMMASK
req.alt-loc: rilapitypes.h
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
req.typenames: RILOPERATORNAMESPARAMMASK
req.product: Windows 10 or later.
---

# RILOPERATORNAMESPARAMMASK enumeration



## -description

## -syntax

````
enum RILOPERATORNAMESPARAMMASK {
  RIL_PARAM_ON_LONGNAME      = 0x00000001, 
  RIL_PARAM_ON_SHORTNAME     = 0x00000002, 
  RIL_PARAM_ON_NUMNAME       = 0x00000004, 
  RIL_PARAM_ON_COUNTRY_CODE  = 0x00000008, 
  RIL_PARAM_ON_SYSTEMTYPE    = 0x00000010, 
  RIL_PARAM_ON_ALL           = 0x0000001F 

};
````


## -enum-fields

### -field RIL_PARAM_ON_LONGNAME


### -field RIL_PARAM_ON_SHORTNAME


### -field RIL_PARAM_ON_NUMNAME


### -field RIL_PARAM_ON_COUNTRY_CODE


### -field RIL_PARAM_ON_SYSTEMTYPE


### -field RIL_PARAM_ON_ALL


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILOPERATORNAMESPARAMMASK enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

