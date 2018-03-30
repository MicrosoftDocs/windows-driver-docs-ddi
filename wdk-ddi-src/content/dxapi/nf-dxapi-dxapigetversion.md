---
UID: NF:dxapi.DxApiGetVersion
title: DxApiGetVersion function
author: windows-driver-content
description: Do not use the DxApiGetVersion function; use the DxApi function along with the DD_DXAPI_GETVERSIONNUMBER function identifier instead.The DxApiGetVersion function returns a Direct Sound version number of 4.02.
old-location: display\dxapigetversion.htm
old-project: display
ms.assetid: f9d441a5-46b5-4da8-aa7e-f4f45eb733d4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DxApiGetVersion, DxApiGetVersion function [Display Devices], ddfncs_72fbedfa-d63f-462a-a6c4-862c6815f1c1.xml, display.dxapigetversion, dxapi/DxApiGetVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dxapi.h
req.include-header: Dxapi.h
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
req.lib: Dxapi.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Dxapi.lib
-	Dxapi.dll
api_name:
-	DxApiGetVersion
product: Windows
targetos: Windows
req.typenames: DRMRIGHTS, *PDRMRIGHTS
---

# DxApiGetVersion function


## -description


Do not use the <b>DxApiGetVersion</b> function; use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557364">DxApi</a> function along with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550637">DD_DXAPI_GETVERSIONNUMBER</a> function identifier instead.

The <b>DxApiGetVersion</b> function returns a Direct Sound version number of 4.02.


## -parameters






## -returns



Returns the major and minor version numbers of Direct Sound as 4 and 2 respectively.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549530">DDGETVERSIONNUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550637">DD_DXAPI_GETVERSIONNUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557364">DxApi</a>
 

 

