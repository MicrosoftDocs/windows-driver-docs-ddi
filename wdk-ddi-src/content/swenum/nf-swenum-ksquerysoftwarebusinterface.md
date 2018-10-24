---
UID: NF:swenum.KsQuerySoftwareBusInterface
title: KsQuerySoftwareBusInterface function
author: windows-driver-content
description: The KsQuerySoftwareBusInterface function creates a buffer from the paged pool and copies the reference string associated with the demand-load bus enumerator object's PDO into the buffer.
old-location: stream\ksquerysoftwarebusinterface.htm
tech.root: stream
ms.assetid: 2a4dd5a8-e9cc-4404-8031-5091ff2aa50d
ms.date: 04/23/2018
ms.keywords: KsQuerySoftwareBusInterface, KsQuerySoftwareBusInterface function [Streaming Media Devices], ksfunc_58ad39a9-6e7b-416b-9ca6-a5a92bb0a7fc.xml, stream.ksquerysoftwarebusinterface, swenum/KsQuerySoftwareBusInterface
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	swenum.h
api_name:
-	KsQuerySoftwareBusInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsQuerySoftwareBusInterface function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsQuerySoftwareBusInterface</b> function creates a buffer from the paged pool and copies the reference string associated with the demand-load bus enumerator object's PDO into the buffer. It is the caller's responsibility to free the buffer using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>. 


## -parameters




### -param PnpDeviceObject [in]

Pointer to the demand-load bus enumerator's device object.


### -param BusInterface [out]

Pointer to the demand-load bus enumerator's interface.


## -returns



Returns STATUS_SUCCESS if the request is handled. Otherwise, it returns an appropriate error code.




## -remarks



A minidriver can access this function through the <b>QueryReferenceString</b> member of the BUS_INTERFACE_SWENUM structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557589">BUS_INTERFACE_SWENUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561678">KsDereferenceSoftwareBusObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566763">KsReferenceSoftwareBusObject</a>
 

 

