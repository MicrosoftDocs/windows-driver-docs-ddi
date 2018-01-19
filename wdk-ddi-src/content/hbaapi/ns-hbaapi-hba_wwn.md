---
UID: NS:hbaapi.HBA_wwn
title: HBA_wwn
author: windows-driver-content
description: The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA.
old-location: storage\hba_wwn.htm
old-project: storage
ms.assetid: 84441fde-1d66-4f76-86b7-dccd792afd0f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_wwn, *PHBA_WWN, HBA_WWN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_WWN
req.alt-loc: hbaapi.h
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
req.typenames: *PHBA_WWN, HBA_WWN
---

# HBA_wwn structure



## -description
The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA. 



## -syntax

````
typedef struct HBA_wwn {
  HBA_UINT8 wwn[8];
} HBA_WWN, *PHBA_WWN;
````


## -struct-fields

### -field wwn

Contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA. .


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_adapterattributes.md">HBA_AdapterAttributes</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_wwn structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

