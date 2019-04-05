---
UID: NF:bdasup.BdaUninitFilter
title: BdaUninitFilter function (bdasup.h)
description: The BdaUninitFilter function removes the BDA filter context from the associated filter instance.
old-location: stream\bdauninitfilter.htm
tech.root: stream
ms.assetid: c74f5633-49bf-4c8d-8702-89723067753a
ms.date: 04/23/2018
ms.keywords: BdaUninitFilter, BdaUninitFilter function [Streaming Media Devices], bdaref_68d86dcd-9a84-4c5f-acf5-8174ab3ba6d8.xml, bdasup/BdaUninitFilter, stream.bdauninitfilter
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Bdasup.lib
- Bdasup.dll
api_name:
- BdaUninitFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaUninitFilter function


## -description


The <b>BdaUninitFilter</b> function removes the BDA filter context from the associated filter instance. 


## -parameters




### -param pKSFilter [in]

Points to the filter from which to remove the BDA filter context.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



The <b>BdaUninitFilter</b> function exists only to support legacy drivers and is, therefore, obsolete. That is, new BDA minidriver implementations should not call <b>BdaUninitFilter</b>. 

In Windows XP and later, the BDA support driver (<i>Bdasup.sys</i>) automatically handles removing the BDA filter context associated with a filter instance. When a BDA minidriver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556464">BdaInitFilter</a>, the BDA support driver creates its own BDA filter context. This BDA filter context is hidden from the BDA minidriver. However, when required, the BDA support driver can access this BDA filter context. The BDA support driver adds a pointer to this BDA filter context to the object bag for the associated <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> object. When the associated KSFILTER object is destroyed, AVStream requests that the BDA support driver delete this BDA filter context from the object bag. In this way, the BDA support driver can destroy this BDA filter context without requiring intervention by the BDA minidriver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556464">BdaInitFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>
 

 

