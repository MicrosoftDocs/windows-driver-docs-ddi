---
UID: NF:bdasup.BdaInitFilter
title: BdaInitFilter function
author: windows-driver-content
description: The BdaInitFilter function initializes the BDA filter context associated with a filter instance.
old-location: stream\bdainitfilter.htm
tech.root: stream
ms.assetid: d6f5c6e5-d944-42a6-bfc2-decc7606cba1
ms.date: 4/23/2018
ms.keywords: BdaInitFilter, BdaInitFilter function [Streaming Media Devices], bdaref_9ad4e7ef-1880-4233-83c5-4d066c8f26e5.xml, bdasup/BdaInitFilter, stream.bdainitfilter
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Bdasup.lib
-	Bdasup.dll
api_name:
-	BdaInitFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaInitFilter function


## -description


The <b>BdaInitFilter</b> function initializes the BDA filter context associated with a filter instance. 


## -parameters




### -param pKSFilter [in]

Points to the filter in which to initialize the BDA filter context.


### -param pBdaFilterTemplate [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556523">BDA_FILTER_TEMPLATE</a> structure that describes the filter template for the BDA device. To determine topology for and configure the initialized filter, the network provider uses information referenced in this BDA_FILTER_TEMPLATE structure. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaInitFilter</b> function to initialize an instance of a filter using a specific BDA filter template and a filter factory that was previously created through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556438">BdaCreateFilterFactory</a> function. The BDA minidriver can subsequently use this filter instance in calls to other BDA support functions, such as, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556445">BdaCreatePin</a>. 

When a BDA minidriver calls <b>BdaInitFilter</b>, the BDA support driver (<i>Bdasup.sys</i>) creates its own BDA filter context. This BDA filter context is hidden from the BDA minidriver. However, when required, the BDA support driver can access this BDA filter context. The BDA support driver adds a pointer to this BDA filter context to the object bag for the associated <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> object. When the associated KSFILTER object is destroyed, AVStream requests that the BDA support driver delete this BDA filter context from the object bag. In this way, the BDA support driver can destroy this BDA filter context without requiring intervention by the BDA minidriver. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556523">BDA_FILTER_TEMPLATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556438">BdaCreateFilterFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556445">BdaCreatePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>
 

 

