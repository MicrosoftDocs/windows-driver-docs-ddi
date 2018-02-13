---
UID: NE:bthddi._SCO_LINK_TYPE
title: "_SCO_LINK_TYPE"
author: windows-driver-content
description: The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a ScoIndicationRemoteConnect indication event is processed.
old-location: bltooth\sco_link_type.htm
old-project: bltooth
ms.assetid: 6867a88d-6bce-46eb-894a-cc034a1c3ece
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bthddi/ScoLinkType, bltooth.sco_link_type, eScoLinkType, *PSCO_LINK_TYPE, ScoLinkType, bthddi/PSCO_LINK_TYPE, PSCO_LINK_TYPE, bth_enums_c5b9357f-7046-4115-a8a7-add459e59f27.xml, _SCO_LINK_TYPE, PSCO_LINK_TYPE enumeration pointer [Bluetooth Devices], bthddi/eScoLinkType, bthddi/SCO_LINK_TYPE, SCO_LINK_TYPE enumeration [Bluetooth Devices], SCO_LINK_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	SCO_LINK_TYPE
product: Windows
targetos: Windows
req.typenames: "*PSCO_LINK_TYPE, SCO_LINK_TYPE"
---

# _SCO_LINK_TYPE enumeration


## -description


The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a 
  <b>ScoIndicationRemoteConnect</b> indication event is processed.


## -syntax


````
typedef enum _SCO_LINK_TYPE { 
  ScoLinkType   = 0x00,
  eScoLinkType  = 0x02
} SCO_LINK_TYPE, *PSCO_LINK_TYPE;
````


## -enum-fields




### -field ScoLinkType

This value indicates that the link used by the connection is a SCO link.


### -field eScoLinkType

This value indicates that the link used by the connection is an eSCO link.


## -remarks



The 
    <a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">SCO_INDICATION_PARAMETERS</a> structure
    uses this enumeration.




## -see-also

<a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">SCO_INDICATION_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SCO_LINK_TYPE enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

