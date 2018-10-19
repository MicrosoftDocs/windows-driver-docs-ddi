---
UID: NE:wdfrequest._WDF_REQUEST_REUSE_FLAGS
title: "_WDF_REQUEST_REUSE_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_REUSE_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_flags.htm
tech.root: wdf
ms.assetid: 3d1f8f38-b875-4661-9941-4dec28b7e8fb
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_4b91ca45-4dbb-4942-83ce-72ca10170932.xml, WDF_REQUEST_REUSE_FLAGS, WDF_REQUEST_REUSE_FLAGS enumeration, WDF_REQUEST_REUSE_NO_FLAGS, WDF_REQUEST_REUSE_SET_NEW_IRP, _WDF_REQUEST_REUSE_FLAGS, kmdf.wdf_request_reuse_flags, wdf.wdf_request_reuse_flags, wdfrequest/WDF_REQUEST_REUSE_FLAGS, wdfrequest/WDF_REQUEST_REUSE_NO_FLAGS, wdfrequest/WDF_REQUEST_REUSE_SET_NEW_IRP
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_REUSE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_REUSE_FLAGS
---

# _WDF_REQUEST_REUSE_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_REUSE_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.


## -enum-fields




### -field WDF_REQUEST_REUSE_NO_FLAGS

No flags are set.


### -field WDF_REQUEST_REUSE_SET_NEW_IRP

The <b>NewIrp</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure is valid.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a>
 

 

