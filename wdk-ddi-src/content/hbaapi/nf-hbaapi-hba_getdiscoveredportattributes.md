---
UID: NF:hbaapi.HBA_GetDiscoveredPortAttributes
title: HBA_GetDiscoveredPortAttributes function
description: The HBA_GetDiscoveredPortAttributes routine retrieves the attributes for a specified remote fibre channel port.
old-location: storage\hba_getdiscoveredportattributes.htm
tech.root: storage
ms.assetid: 64c6ed50-a4b9-4a8c-b38c-b2fcdf5ccee9
ms.date: 03/29/2018
ms.keywords: HBA_GetDiscoveredPortAttributes, HBA_GetDiscoveredPortAttributes routine [Storage Devices], fibreHBA_rtns_3f74a187-728d-4534-8ad8-29e1a9b0add5.xml, hbaapi/HBA_GetDiscoveredPortAttributes, storage.hba_getdiscoveredportattributes
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
-	HBA_GetDiscoveredPortAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetDiscoveredPortAttributes function


## -description


The <b>HBA_GetDiscoveredPortAttributes</b> routine retrieves the attributes for a specified remote fibre channel port.


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA on which the port is located.  </p>


### -param PortIndex [in]

Indicates the index of the local port of type Nx_Port through which to query the discovered remote port. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param DiscoveredPortIndex [in]

Indicates the index of the remote port to query. 


### -param PortAttributes

<p>Contains a structure of type <a href="https://msdn.microsoft.com/library/Ff557107(v=VS.85).aspx"><b>HBA_PortAttributes</b></a> that reports the port attributes. </p>




## -returns



The <b>HBA_GetDiscoveredPortAttributes</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. 




## -remarks



The <b>HBA_GetDiscoveredPortAttributes</b> library routine corresponds to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a> WMI method. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557107">HBA_PortAttributes</a>
 

 

