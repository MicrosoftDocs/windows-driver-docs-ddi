---
UID: NF:hbaapi.HBA_GetAdapterPortAttributes
title: HBA_GetAdapterPortAttributes function
author: windows-driver-content
description: The HBA_GetAdapterPortAttributes routine retrieves the attributes for a specified remote fibre channel port.
old-location: storage\hba_getadapterportattributes.htm
old-project: storage
ms.assetid: f1f5dc4e-8069-4e3e-94a0-a9a7c359bdb4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_GetAdapterPortAttributes, HBA_GetAdapterPortAttributes routine [Storage Devices], fibreHBA_rtns_c49b4806-e5cf-40fa-a166-8f2ab58259ae.xml, hbaapi/HBA_GetAdapterPortAttributes, storage.hba_getadapterportattributes
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetAdapterPortAttributes
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetAdapterPortAttributes function


## -description


The <b>HBA_GetAdapterPortAttributes</b> routine retrieves the attributes for a specified remote fibre channel port. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetAdapterPortAttributes(
  _In_  HBA_HANDLE         HbaHandle,
  _In_  HBA_UINT32         PortIndex,
  _Out_ HBA_PORTATTRIBUTES *PortAttributes
);
````


## -parameters




### -param Handle

TBD


### -param PortIndex [in]

Indicates which remote port to query on the HBA specified by <i>HbaHandle</i>. 


### -param PortAttributes [out]

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a> that, on return, contains the attributes of the remote port with an index of <i>PortIndex </i>on the HBA specified by <i>HbaHandle. </i>


#### - HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


## -returns



The <b>HBA_GetAdapterPortAttributes</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. A value of HBA_STATUS_OK indicates that the operation succeeded. A value of HBA_STATUS_ERROR indicates that an unspecified error occurred that prevented the retrieval of the port attributes. 




## -remarks



The <b>HBA_GetAdapterPortAttributes</b> routine retrieves attributes for remote ports of type Nx_Port. For a definition of Nx_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetAdapterPortAttributes routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

