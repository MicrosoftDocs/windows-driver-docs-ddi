---
UID: NF:hbaapi.HBA_GetPortAttributesByWWN
title: HBA_GetPortAttributesByWWN function
author: windows-driver-content
description: The HBA_GetPortAttributesByWWN routine retrieves the attributes for the port specified by the indicated port name.
old-location: storage\hba_getportattributesbywwn.htm
old-project: storage
ms.assetid: 79d63b5e-78b0-452a-aa84-695c59a7d4a5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbaapi/HBA_GetPortAttributesByWWN, fibreHBA_rtns_2cd8e0da-90d5-41bb-8bd9-ab2ee26ec772.xml, HBA_GetPortAttributesByWWN, HBA_GetPortAttributesByWWN routine [Storage Devices], storage.hba_getportattributesbywwn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_GetPortAttributesByWWN
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetPortAttributesByWWN function


## -description


The <b>HBA_GetPortAttributesByWWN</b> routine retrieves the attributes for the port specified by the indicated port name. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetPortAttributesByWWN(
  _In_  HBA_HANDLE         HbaHandle,
  _In_  HBA_WWN            PortWWN,
  _Out_ HBA_PORTATTRIBUTES *HbaPortAttributes
);
````


## -parameters




### -param Handle

TBD


### -param PortWWN [in]

Contains the worldwide name (WWN) of the port whose attributes to retrieve. For a definition of worldwide names, see the T11 committee's <i>Fibre Channel HBA API </i>specification .


### -param PortAttributes

TBD




#### - HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located.  


#### - HbaPortAttributes [out]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a> that holds the port attributes: 


## -returns



The <b>HBA_GetPortAttributesByWWN</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. 




## -remarks



The <b>HBA_GetPortAttributesByWWN</b> routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a> WMI method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a>



<a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetPortAttributesByWWN routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

