---
UID: NS:61883._UNIT_DDI_VERSION
title: "_UNIT_DDI_VERSION"
author: windows-driver-content
description: The UNIT_DDI_VERSION structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve the current 61883 DDI version.
old-location: ieee\unit_ddi_version.htm
old-project: IEEE
ms.assetid: 421ed5b2-389d-4099-b241-d952fb7e842d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 61883_structures_dacbe4af-54fd-4b96-89e2-6954a623e75d.xml, _UNIT_DDI_VERSION, PUNIT_DDI_VERSION structure pointer [Buses], 61883/UNIT_DDI_VERSION, UNIT_DDI_VERSION, UNIT_DDI_VERSION structure [Buses], PUNIT_DDI_VERSION, *PUNIT_DDI_VERSION, IEEE.unit_ddi_version, 61883/PUNIT_DDI_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	61883.h
apiname:
-	UNIT_DDI_VERSION
product: Windows
targetos: Windows
req.typenames: UNIT_DDI_VERSION, *PUNIT_DDI_VERSION
---

# _UNIT_DDI_VERSION structure


## -description


The UNIT_DDI_VERSION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve the current 61883 DDI version.


## -syntax


````
typedef struct _UNIT_DDI_VERSION {
  ULONG Version;
} UNIT_DDI_VERSION, *PUNIT_DDI_VERSION;
````


## -struct-fields




#### - Version

The current 61883 DDI version.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20UNIT_DDI_VERSION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

