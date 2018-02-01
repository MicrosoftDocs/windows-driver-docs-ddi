---
UID: NS:hbapiwmi._GetDiscoveredPortAttributes_OUT
title: "_GetDiscoveredPortAttributes_OUT"
author: windows-driver-content
description: The GetDiscoveredPortAttributes_OUT structure is used to report the output parameter data of the GetDiscoveredPortAttributes WMI method to the WMI client.
old-location: storage\getdiscoveredportattributes_out.htm
old-project: storage
ms.assetid: 7a6ae185-2f91-4285-b540-61130aef464c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetDiscoveredPortAttributes_OUT structure [Storage Devices], hbapiwmi/GetDiscoveredPortAttributes_OUT, _GetDiscoveredPortAttributes_OUT, GetDiscoveredPortAttributes_OUT, PGetDiscoveredPortAttributes_OUT structure pointer [Storage Devices], *PGetDiscoveredPortAttributes_OUT, structs-Fibre_611d9a0e-b0dc-472e-9bec-3902412e8ec4.xml, storage.getdiscoveredportattributes_out, hbapiwmi/PGetDiscoveredPortAttributes_OUT, PGetDiscoveredPortAttributes_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	GetDiscoveredPortAttributes_OUT
product: Windows
targetos: Windows
req.typenames: GetDiscoveredPortAttributes_OUT, *PGetDiscoveredPortAttributes_OUT
---

# _GetDiscoveredPortAttributes_OUT structure


## -description


The GetDiscoveredPortAttributes_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a> WMI method to the WMI client. 


## -syntax


````
typedef struct _GetDiscoveredPortAttributes_OUT {
  ULONG                         HBAStatus;
  MSFC_HBAPortAttributesResults PortAttributes;
} GetDiscoveredPortAttributes_OUT, *PGetDiscoveredPortAttributes_OUT;
````


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.


### -field PortAttributes

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_msfc_hbaportattributesresults.md">MSFC_HBAPortAttributesResults</a> that holds the port attributes to report.


## -remarks


The WMI tool suite generates a declaration of the GetDiscoveredPortAttributes_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetDiscoveredPortAttributes_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

