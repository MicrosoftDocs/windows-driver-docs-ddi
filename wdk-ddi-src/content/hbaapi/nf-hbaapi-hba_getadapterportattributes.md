---
UID: NF:hbaapi.HBA_GetAdapterPortAttributes
title: HBA_GetAdapterPortAttributes function
author: windows-driver-content
description: The HBA_GetAdapterPortAttributes routine retrieves the attributes for a specified remote fibre channel port.
old-location: storage\hba_getadapterportattributes.htm
old-project: storage
ms.assetid: f1f5dc4e-8069-4e3e-94a0-a9a7c359bdb4
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
product:
- Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetAdapterPortAttributes function


## -description


The <b>HBA_GetAdapterPortAttributes</b> routine retrieves the attributes for a specified remote fibre channel port. 


## -parameters




### -param Handle

TBD


### -param PortIndex [in]

Indicates which remote port to query on the HBA specified by <i>HbaHandle</i>. 


### -param PortAttributes [out]

Pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557107">HBA_PortAttributes</a> that, on return, contains the attributes of the remote port with an index of <i>PortIndex </i>on the HBA specified by <i>HbaHandle. </i>


#### - HbaHandle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


## -returns



The <b>HBA_GetAdapterPortAttributes</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. A value of HBA_STATUS_OK indicates that the operation succeeded. A value of HBA_STATUS_ERROR indicates that an unspecified error occurred that prevented the retrieval of the port attributes. 




## -remarks



The <b>HBA_GetAdapterPortAttributes</b> routine retrieves attributes for remote ports of type Nx_Port. For a definition of Nx_Port, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557107">HBA_PortAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

