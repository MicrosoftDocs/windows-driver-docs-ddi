---
UID: NF:bdasup.BdaUninitFilter
title: BdaUninitFilter function
author: windows-driver-content
description: The BdaUninitFilter function removes the BDA filter context from the associated filter instance.
old-location: stream\bdauninitfilter.htm
old-project: stream
ms.assetid: c74f5633-49bf-4c8d-8702-89723067753a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.bdauninitfilter, BdaUninitFilter, bdaref_68d86dcd-9a84-4c5f-acf5-8174ab3ba6d8.xml, BdaUninitFilter function [Streaming Media Devices], bdasup/BdaUninitFilter
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Bdasup.lib
-	Bdasup.dll
apiname:
-	BdaUninitFilter
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# BdaUninitFilter function


## -description


The <b>BdaUninitFilter</b> function removes the BDA filter context from the associated filter instance. 


## -syntax


````
NTSTATUS BdaUninitFilter(
  _In_ PKSFILTER pKSFilter
);
````


## -parameters




### -param pKSFilter [in]

Points to the filter from which to remove the BDA filter context.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



The <b>BdaUninitFilter</b> function exists only to support legacy drivers and is, therefore, obsolete. That is, new BDA minidriver implementations should not call <b>BdaUninitFilter</b>. 

In Windows XP and later, the BDA support driver (<i>Bdasup.sys</i>) automatically handles removing the BDA filter context associated with a filter instance. When a BDA minidriver calls <a href="..\bdasup\nf-bdasup-bdainitfilter.md">BdaInitFilter</a>, the BDA support driver creates its own BDA filter context. This BDA filter context is hidden from the BDA minidriver. However, when required, the BDA support driver can access this BDA filter context. The BDA support driver adds a pointer to this BDA filter context to the object bag for the associated <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> object. When the associated KSFILTER object is destroyed, AVStream requests that the BDA support driver delete this BDA filter context from the object bag. In this way, the BDA support driver can destroy this BDA filter context without requiring intervention by the BDA minidriver.




## -see-also

<a href="..\bdasup\nf-bdasup-bdainitfilter.md">BdaInitFilter</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaUninitFilter function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

