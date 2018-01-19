---
UID: NE:rilapitypes.RILIMSSYSTEMTYPE
title: RILIMSSYSTEMTYPE
author: windows-driver-content
description: The RILIMSSYSTEMTYPE enumeration has the following values.
old-location: netvista\rilimssystemtype.htm
old-project: netvista
ms.assetid: e1f5dde2-8e45-4904-bbf3-bd2358f95a5b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILIMSSYSTEMTYPE, RILIMSSYSTEMTYPE
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
req.alt-api: RILIMSSYSTEMTYPE
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
req.typenames: RILIMSSYSTEMTYPE
req.product: Windows 10 or later.
---

# RILIMSSYSTEMTYPE enumeration



## -description

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


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILIMSSYSTEMTYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

