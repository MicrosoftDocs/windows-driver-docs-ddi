---
UID: NF:swenum.KsReferenceSoftwareBusObject
title: KsReferenceSoftwareBusObject function
description: The KsReferenceSoftwareBusObject function increments the reference count of the demand-load bus enumerator object's PDO.
old-location: stream\ksreferencesoftwarebusobject.htm
tech.root: stream
ms.assetid: 56c7ce80-36da-4991-a640-f87b712f683e
ms.date: 04/23/2018
ms.keywords: KsReferenceSoftwareBusObject, KsReferenceSoftwareBusObject function [Streaming Media Devices], ksfunc_38a63d2d-e988-474d-890b-dd9a2aeeaff4.xml, stream.ksreferencesoftwarebusobject, swenum/KsReferenceSoftwareBusObject
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsReferenceSoftwareBusObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsReferenceSoftwareBusObject function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsReferenceSoftwareBusObject</b> function increments the reference count of the demand-load bus enumerator object's PDO. 


## -parameters




### -param Header [in]

Pointer to the device header (extension) of the demand-load bus enumerator.


## -returns



Returns STATUS_SUCCESS if the request is handled. Otherwise, it returns an appropriate error code.




## -remarks



A minidriver can access this function through the <b>ReferenceDeviceObject</b> member of the BUS_INTERFACE_SWENUM structure.

The device object remains active and enumerated until the reference count returns to 0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557589">BUS_INTERFACE_SWENUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561678">KsDereferenceSoftwareBusObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566749">KsQuerySoftwareBusInterface</a>
 

 

